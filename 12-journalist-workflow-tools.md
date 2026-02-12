# 12 journalist workflow tools

As a reporter, you will likely spend most of your time creating and revising content within Desks or your Custom Workspace(s), in addition to monitoring and searching content for research purposes. Once an admin creates an account for you in Superdesk, you will receive an email with login instructions.

If you haven’t already done so, it would be useful to familiarise yourself with the following chapters:

* [What is Superdesk?](12-journalist-workflow-tools.md#what-is-superdesk?)
* [Dashboards & Widgets](12-journalist-workflow-tools.md#dashboards-and-widgets)
* [Monitoring](12-journalist-workflow-tools.md#monitoring-tab)
* [Superdesk Glossary](12-journalist-workflow-tools.md#heading=h.augg1lln53l3)

When you click on Select Workspace (the Desks menu) in the upper-left corner beside the Hamburger menu, a drop-down list of desks you’ve been assigned to should appear. If you don’t see any Desks in this menu, contact your administrator to set them up.

The Dashboard for each Desk will display widgets configured by your editor or admin. You can customise the Dashboard widgets on your Custom Workspace Dashboard.

The Monitoring View is a space where journalists or production staff can keep up-to-date on the content in each work Stages, create new items and move content between stages. The Monitoring View can also be set up to show Saved Searches. The content of the Monitoring View tab is set up by your desk administrator, in the Desks section of the Hamburger menu.

### Content Workflow

{% stepper %}
{% step %}
### Create a new item

* Make sure you’re on the Desk where the item should be created (check the Desks menu at the top of the Superdesk interface). Alternatively, create a new item in your Personal Space if it’s not intended to be shared right away.
* Click the Monitoring icon (second icon on the Workspace Panel) to enter the Monitoring workspace.
* Click the Create icon in the upper-right corner of the Superdesk interface.
* Depending on which content profiles are assigned to your desk, choose the content profile or template you want to create from.
{% endstep %}

{% step %}
### Enter content and save

* Enter metadata and some text.
* Click the SAVE button in the top-right corner to save as a draft.
* Articles are saved to the Desk you are currently working on. If you are working in a custom workspace, the article will be saved to the current user’s default desk.

You can keep an article open but minimise it by clicking the minimise icon located beside the SAVE button at the top of the article editing pane.
{% endstep %}

{% step %}
### Locks and open items

* If you don’t close the article, it will lock, preventing other users from updating it (senior staff can override this).
* All your open items remain visible in the Workspace Bar at the bottom of the Superdesk interface.
* If a user session hasn’t been updated in four hours, the session is terminated and the lock is dropped.
* While you are editing an item, it is locked; this is denoted by a red stripe that appears next to the article entry in the Monitoring tab.
{% endstep %}

{% step %}
### Autosave and offline recovery

* Changes are autosaved both on the server and locally.
* If you lose internet connection, you can restore your work once a connection to the server is re-established, though there may be issues if the file has been modified during the disconnection.
{% endstep %}
{% endstepper %}

### Research & Multi-Pane Workflow

The Search feature allows users to navigate multimedia from any repository Superdesk is aware of: various news agency feeds, RSS, emails and other sources. These sources are set up by the Superdesk administrator. If you cannot find items from a desired source, notify your administrator.

Superdesk’s multi-pane workflow enables users to have a Monitoring or Search window for research open at the same time as an article entry. This makes it convenient to work on an article and easily switch context to look up information in an archive, for example. Users can also have multiple article entry windows open simultaneously.

### Monitoring Issues & Saved Searches

To monitor incoming RSS content or content about a particular issue, you can set up a Monitoring widget in your Custom Workspace.

{% stepper %}
{% step %}
### Create and save an Advanced Search

* Click the Search icon on the Workspace Panel and set parameters for your Advanced Search.
* After running the search, click the blue Save Search button that appears at the bottom of the screen.
* Turn on the Global Read toggle if you want the Saved Search to be available in a Monitoring widget outside your Custom Workspace. (Saved Searches used only in your Custom Workspace don't need Global Read.)
{% endstep %}

{% step %}
### Use the Saved Search

* Click the Saved tab of the Advanced Search panel to see your Saved Search. Note: you can save a search even if it currently returns no content; you’ll be alerted when matching content arrives.
{% endstep %}

{% step %}
### Add a Monitoring widget for a Saved Search

* Click the house-shaped Dashboard icon on the Workspace Panel.
* Click the blue Create button in the top-right corner to add a new widget.
* Select Monitoring Widget, then Add this Widget, then click Done.
* To adjust settings, click the gear in the top-right corner of the widget on the Dashboard.
* Select the Saved Searches tab and pick from the list of Global Saved Searches. Toggle a Saved Search on (blue) or off (grey).
* Use Reorder Sections to arrange multiple searches and desk Stages; adjust the number of items to display for each section.
{% endstep %}
{% endstepper %}

### Updating Content

To resume working on an article after it’s been closed, find the content via the Monitoring view search feature.

From the Monitoring View you can also use the Quick Search Filter (click the search icon in the top-left corner of the Monitoring pane) to quickly filter through items in a Saved Search or other lists.

Once the desired article appears, hover over it to reveal the Action Menu and click Edit to open the item in a new pane.

### Bundling Images and Text Items Together

There are several ways to bundle images and text together:

* Create a package and insert both images and text items into the package.
* Insert images into the main body of an article directly.
* Add images as attachments when an article is open for editing.

Ask your Editor which method they prefer. You can read about [creating Packages](12-journalist-workflow-tools.md#packages) and [inserting media in the body of an article](12-journalist-workflow-tools.md#making-new-articles) in other parts of this manual.

### Sending Drafts

This is the Send to/Publish icon.

{% stepper %}
{% step %}
### From Personal Space to a Desk

* If you created an item in your Personal Space, when ready you can send it to a Desk for review by clicking the Send to button in the top-right corner of the article editing window.
* If you created the article on a Desk, it will automatically be visible to others.
{% endstep %}

{% step %}
### Sending to publishing or stages

* Depending on your permissions, you may be able to send the item to the publishing queue using the Send to/Publish button.
* If not ready to send, click SAVE, then CLOSE to revisit the article later.
* To move a content item into another stage, click Send to; a pop-up appears allowing you to select the destination Desk and work stage (e.g., Bureau chief in, Bureau out).
{% endstep %}

{% step %}
### Additional Send to options

* Use the pane to set an Embargo notice or a publishing schedule. Note: an Embargo does not prevent an article from being published.
* News items or packages can be sent to a different stage of a Desk or to another desk, and can also be published (publishing can be scheduled).
* Once Published, items can only be updated or killed.
{% endstep %}

{% step %}
### Updates and Kills

* Update: creates a new article with the same metadata (bylines, dateline, headline, abstract, priority, urgency, place, subject and category); takekey becomes "update". Updates cannot be performed on picture items or packages.
* Kill: used to stop clients from using content you sent them; they are required to remove the content once you issue a kill.
{% endstep %}
{% endstepper %}

### Spiking

Spiking an item marks it for removal from the Desk workflow without deleting the information (so it can be used later). To view all spiked items, click the Spiked Items icon on the Workspace Panel.

To Spike an item, click the Action menu of the article and select Spike Item. Note that published items cannot be Spiked. Items spiked from your Personal Space are permanently deleted.

### Other Useful Features & Tools

#### Templates

Templates let you save an article with a complete copy of its metadata via the Action menu at the top of the article editing window by selecting Save as template.

When selecting Save as Template, a window prompts you to name the template and assign it to a Desk.

* Creation templates create content with a specific profile (e.g., general news vs court template).
* Highlights templates configure elements like Headline, Byline, Abstract from multiple articles to be displayed as flat/digest files.

#### Multiedit

The Multiedit button lets you toggle between multiple open content items and display two news items side-by-side in editing mode. You can enable Multiedit from the action menu at the top of the article editing window. You can select up to 12 articles to open in Multiedit mode simultaneously.

#### Highlights

The Highlight icon on the Workspace Panel allows you to view Highlight lists (content indexes, top-10 lists, section features, user-curated lists). Highlights can be generated automatically against user-defined metadata, or set up for manual curation. Highlight lists can be scheduled for publication or distribution. Most journalists will not have permission to add items to a Highlight list.

#### Versioning

While an item is open for editing, click the Versioning icon in the Editor Sidebar to display previous saves or revert to earlier versions.

#### Annotations

Annotations allow journalists to add information to articles. They can be created in the Hamburger menu (Annotations Library) or within the editor while creating an article.

To add an annotation to text in the article body, highlight the text and click the annotations button. [Read more about Annotations](12-journalist-workflow-tools.md#using-the-annotations-feature).

### Custom Workspaces and Personal Space

Custom Workspaces are configurable individual workspaces accessible from the Desks menu. Custom Workspaces have their own Dashboards and Monitoring tabs, making it possible to monitor several Desks in one place.

Customising your Custom Workspace Dashboard helps monitor several projects without switching between Desks. Only you can access your Custom Workspaces, so you can customise the Dashboard and Monitoring tab to suit your workflow. Desk Dashboards have widgets determined by the Desk manager.

Personal Space is an icon located on the Workspace Panel. Clicking it displays all the articles and items you created in your Personal Space. Only you can view or edit these items. To create a new Personal Item, click the Create icon in the top-right corner of the Personal Space. You can send Personal Items to a Desk workflow using the purple Send to button in the article editing window.

### User Profile Settings

Click your user icon in the upper-right corner of the Superdesk interface and select Profile to view and adjust profile settings. From here you can:

* View an overview of your profile information
* Set preferences and contact information
* View your privileges and activity stream

User privileges are set by administrators.

### Comments

When an article is open for editing, users can add Comments to each news item with Twitter-like @mentions.

This is useful for alerting other Desks or users quickly.

&#x20;This is the Comments button in the Editor Sidebar.

* Comments can be viewed in the Editor Sidebar when an article is open.
* Inline Comments can be added to the Body of a news item using the Inline Comments feature to reference specific parts of the text.

### Mark for User

As of Superdesk version 1.33, Superdesk includes a Mark for User feature to keep track of news items requiring a user's attention. Items can be marked for users:

* From the action menu of an item in any list view (Monitoring or Highlights).
* From the action menu of an item in the Editor or Preview pane.
* Using the icons at the top of the Monitoring pane when multiple items are selected.

Users can access items marked for them from the menu to the left of their user icon, or by clicking the Marked for Me button at the top of the Monitoring pane for their current Desk. The info bubble on the Marked for Me button shows how many items are assigned to you in general or within the current Desk.

* Clicking an item in the Marked for Me list opens it in the Editor unless the item is locked by another user.
* Spiked and locked items cannot be marked.
* Only users with mark-for-user privileges can perform this action.
* When marking content for a user, the online status indicator is shown on user avatars so you can see whether the target user is currently online.
* The marked user receives a notification in the Superdesk interface and an email notification.
* When an item is marked for a user, a new version of the content item is automatically created so the user receives the latest copy and to prevent loss of unsaved changes.
