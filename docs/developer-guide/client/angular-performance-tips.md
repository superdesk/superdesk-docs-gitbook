# angular performance tips

This document contains various AngularJS performance tips and the rationale behind them.

{% hint style="info" %}
These tips are specifically for the legacy AngularJS parts of Superdesk. Modern React components should follow React best practices.
{% endhint %}

## Avoid unnecessary DOM manipulations in ng-repeat with `track by`

Consider a common scenario, when you retrieve a bunch of items from the server and list them on the screen:

```javascript
// inside a controller
$scope.searchResults = SearchService.findItems(...);
```

Template:

```html
<div ng-repeat="item in searchResults">
  <h3>{{item.title}}</h3>
  <p>{{item.description}}</p>
</div>
```

Behind the scenes, Angular needs to link the DOM nodes with the items in the collection (searchResults in our case) and for that it needs to distinguish between those items. It does that by adding a special property called `$$hashKey` to each of the items. `$$hashKeys` are unique (they are basically calculated by simply using an auto-incrementing counter).

Now what happens if we submit a new search query and retrieve a new set of items from the server?

Well, the resulting array gets assigned to the `searchResults` variable, Angular calculates `$$hashKeys` for the newly retrieved items, and then it creates new DOM nodes inside of `ng-repeat` and links them to these new items (the old DOM nodes are, of course, destroyed).

The problem: The DOM nodes are destroyed and then re-created even if the new result set contains the same items as before. Since DOM manipulation is a costly operation, this behavior is undesired. Angular doesn't really know that it has received the same items, because their `$$hashKeys` are different (it's an auto-incrementing counter, remember?).

The solution: Tell Angular which items are the same so it won't unnecessarily re-create DOM elements for them. Add a `track by` expression to `ng-repeat`:

```html
<div ng-repeat="item in searchResults track by item.id">
  <h3>{{item.title}}</h3>
  <p>{{item.description}}</p>
</div>
```

Now Angular knows that it can distinguish items by their `id` property instead of relying on computed `$$hashKey` values. It's especially important to use `track by` if your list of items is long and/or the HTML you create for each item is complicated.

The difference in performance can be significant, see a demo here: http://jsfiddle.net/SeKk7/

{% hint style="info" %}
If you don't see a difference, try changing the value in the for loop to 3001... also don't forget to hit the Run button again to load the changed code.
{% endhint %}

Track by was added in Angular 1.2.

## Use one-time bindings wherever possible

One of the biggest bottlenecks in Angular is its digest loop. How does Angular know when a value has changed and update the UI?

Answer: dirty checking. Angular keeps a list of values to watch and fires digest cycles (e.g. when you call `scope.$apply()`). In each cycle it compares remembered values with the current values of objects, variables, etc. If it detects changes, it triggers corresponding change handlers.

Most of the time, Angular adds values to its watch list automatically (e.g. when it encounters `{{expression}}` in a template or when you use directives like `ng-show="someCondition"`), and you can also add watches explicitly (`scope.$watch(...)`).

Checking values for changes takes time; if there are too many watches, the application becomes laggy. A rule of thumb is to never have more than \~2000 watches at the same time and ensure all onChange callbacks execute quickly.

The problem: Many values never change once rendered (e.g. page title, item IDs), but Angular still checks them every digest cycle.

The solution: Tell Angular NOT to check values you know will never change. Use one-time bindings (available since Angular 1.3). Prefix an angular expression with a double colon (`::`):

```html
<ul ng-repeat="role in ::userRoles">
  <li>{{::role.id}} {{::role.name}}</li>
</ul>
```

{% hint style="info" %}
Here we assume that the `userRoles` list never changes during a single page load — if that isn't true, remove the double colon in the `ng-repeat` expression.
{% endhint %}

## Use ng-model-options where applicable

Angular 1.3 introduced the `ng-model-options` directive to manipulate how UI changes are propagated.

Imagine a live search textbox: as users type, you send requests to the server and display results.

```html
<input
  ng-model="searchPhrase"
  ng-change="getResults(searchPhrase)"></input>
```

The problem: If a user types "banana", six search queries are sent ("b", "ba", "ban", "bana", "banan", "banana"). This is overhead; usually only the final query is needed.

The solution: Defer the change event using `ng-model-options`:

```html
<input
  ng-model="searchPhrase"
  ng-model-options="{debounce: 500}"
  ng-change="getResults(searchPhrase)"></input>
```

Now a change is triggered only after 500 ms have elapsed since the last change (i.e., likely when the user finishes typing).

You can also use `ng-model-options` to trigger model changes only on specific JS events (e.g. `blur` instead of `keypress`). See the ng-model-options documentation: https://code.angularjs.org/1.3.14/docs/api/ng/directive/ngModelOptions/

## Understanding the difference between ng-show and ng-if

To conditionally show content, Angular provides `ng-if` and `ng-show` (and `ng-hide`). They work differently:

* `ng-hide="condition"` uses CSS to hide an element if the condition is falsy. The element remains in the DOM, and all expressions on it and its sub-elements are still evaluated on every $digest cycle.
* `ng-if="condition"` removes an element from the DOM entirely, along with all the $watches bound to it.

Thus, if you don't need a part of the page yet, it's better not to have it in the DOM to avoid unnecessary checks in the digest loop. Use `ng-if` when the content doesn't need to be present. If you frequently toggle an element, `ng-show` (CSS show/hide) can be better than repeatedly destroying and recreating DOM via `ng-if`. Use judgment to choose the most suitable approach.

## Avoid (ab)using filters in templates

{% hint style="info" %}
Update: Filters in Angular 1.3 are assumed to be stateless by default — their result depends only on input parameters. Angular optimizes by not invoking stateless filters every $digest cycle unless their input changes.

A filter can be marked as stateful by setting its `$stateful` flag to `true`, e.g. `myFilterFunc.$stateful = true;`
{% endhint %}

For Angular versions prior to 1.3 and for stateful filters, filters can significantly impact $digest performance.

Example:

```html
<ul ng-repeat="user in userList">
  <li>{{user.signatureLine | stripWhitespace | censor | limitTo:100}}</li>
</ul>
```

The problem: These filters are evaluated repeatedly — at least twice per digest cycle — adding overhead on top of dirty-checking `user.signatureLine`. This is especially problematic for complex/time-consuming filters.

Note: In every $digest cycle, the loop runs at least twice — once in response to the triggering event, and at least once more to check for additional model changes made in onModelChange handlers.

The solution: Pre-compute filtered values and provide them to the template:

```html
<ul ng-repeat="user in userList">
  <li>{{user.filteredSignature}}</li>
</ul>
```

Access filters programmatically by injecting and using the `$filter` service:

```javascript
shortenedText = $filter('limitTo')(originalText, 100);
```

## Consider using scope.$digest() instead of scope.$apply()

Sometimes changes happen outside Angular (e.g. manually modifying the DOM in a custom directive). Angular won't notice those changes automatically — you need to trigger a digest.

`$scope.$apply()` evaluates a given expression (if any) and then calls `$rootScope.$digest()`, triggering a $digest on the root scope and all child scopes.

The problem: Visiting all scopes can be redundant when a directive only updates its own `$scope` values that aren't meaningful to ancestor scopes.

The solution: Use `$scope.$digest()` to trigger a $digest only on the current scope and its children, not the whole scope tree.

Caveat: Sometimes you must call `$scope.$apply()` instead (e.g. when ancestor scopes should react to changes in the current scope).

## The dreadful "$digest already in progress" error

This error occurs when you attempt to start a new $digest cycle (e.g. with `$scope.$apply()`) while one is already in progress. A common workaround is wrapping the code in `$timeout(function() {...})`, since `$timeout` executes asynchronously and triggers a new $digest by default.

{% hint style="warning" %}
Please DO NOT use patterns like `if (!$scope.$$phase) $scope.$apply()`. It is considered an anti-pattern and should be avoided.
{% endhint %}

While `$timeout` is fine, `$scope.$evalAsync()` is often better: it will try to execute your code inside the current $digest cycle if one is already in progress, and only schedule a new cycle if necessary. This can avoid unnecessary additional digest cycles.

## See Also

* [Main Client Documentation](file:///docs/developer-guide/client)
* [Architecture Overview](file:///docs/developer-guide/architecture)
* [Contributing Guidelines](file:///docs/contributing)
