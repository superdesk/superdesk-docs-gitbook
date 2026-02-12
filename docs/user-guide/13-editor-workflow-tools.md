# 13 editor workflow tools

As an editor for a particular news beat or Desk, you will likely spend most of your time monitoring issues, editing content submitted by reporters, and publishing content. This section of the Superdesk manual outlines the most useful tools and time-saving features for editors within Superdesk.

Once an admin creates an account for you in Superdesk, you will receive an email with login instructions. The admin will also assign you to the appropriate desk(s) and set your permissions and privileges within Superdesk.

### Editorial Notes

A section for Editorial Notes in a news item’s metadata provides Editors with a means for adding notices to content that will be sent to subscribers. The Editorial Notes is a metadata text box in the article editing window, just above the Headline. In order to use the Editorial Notes, please ensure that the field is enabled in the [Content Profile](13-editor-workflow-tools.md#content-profiles) that you are using.

Editorial Notes can be entered anytime before an article is published, by entering text in the Editorial Notes line of the article metadata.

### Moving Through Workflow & Publishing Content

To publish content or send it to a particular Stage in the content workflow, click the purple _Send To/Publish_ button on the right-hand corner of the article editing window.

A pop-up menu will appear with options to select the destination Desk and Stage (for example Bureau in, Bureau out, Revise), to set an Embargo until a certain date and time, to set a publishing schedule or to publish the content item directly.

{% hint style="info" %}
Stages for each Desk are set up by users with the appropriate permissions in the Hamburger menu.
{% endhint %}

{% hint style="warning" %}
Setting an embargo date does not prevent an item from being published; it marks the item with a date and time before which the item should not be published.
{% endhint %}

### Customised Workflow

Based on workflow configuration (Desks, Stages, etc.) the content can go through various steps of editing and approvals, or it can be published directly if the authors have the appropriate rights/privileges.

Workflow is Desk-specific, so you can have some Desks with users who can publish directly and other Desks with a more complex workflow that suits your newsroom.

### Monitoring Content & Issues on the Dashboard

Monitoring enables you to easily observe desk activity, incoming RSS content and items being produced about a particular issue. This can be done via the Monitoring view (click the Monitoring icon on the Workspace Panel) or by setting up Monitoring widgets on your desk Dashboard.

{% stepper %}
{% step %}
### Adding a Monitoring widget to your Dashboard

1. Click the house-shaped Dashboard icon on the Workspace Panel.
2. If you are assigned to multiple desks, select the correct desk from the Desks menu.
3. Click the Create icon on the top-right corner of the screen.
4. Select _Monitoring_ and then choose _Add this Widget_.
5. Click _DONE_.

To modify the settings of the new widget, click the gear icon located on the top-right corner of the widget.
{% endstep %}

{% step %}
### Configuring the Monitoring widget

* In the monitoring widget settings you'll see a list of desks. Switch the toggles on for the desks you wish to monitor (blue = on, grey = off).
* Select the Stages within each desk that you want to include in the display.
* Arrange the order of the Saved Searches and Desk Stages listed in the widget by clicking the _Reorder Sections_ tab and dragging and dropping them into place.
* Adjust the number of items you’d like to display for each section of the Monitoring widget.

Read more about [Dashboard Widgets](13-editor-workflow-tools.md#heading=h.mie6mqlwhwp5) in other parts of this manual.
{% endstep %}
{% endstepper %}

### Monitoring Saved Searches

Saved searches are a great time-saving feature.

{% stepper %}
{% step %}
### Creating a Saved Search

1. Click the _Search_ icon on the Workspace Panel and set the parameters for your Advanced Search.
2. After the search completes, click the blue SAVE SEARCH button that appears at the bottom of the Advanced Search parameters pane.
3. Toggle Global Read to the on position in the Saved Search window to make it available for your Monitoring widgets.
{% endstep %}

{% step %}
### Adding a Saved Search to a Monitoring widget

1. Add a Monitoring widget as described above.
2. Modify the widget settings and click the _Saved Searches_ tab.
3. Select from the list of Global Saved Searches to include in the widget.
{% endstep %}
{% endstepper %}

### Spiking Items

Spiking an item removes it from the desk workflow. It is not a hard deletion, but a reversible removal. To view spiked items for your current desk, navigate to the Spiked Items icon via the Workspace Panel. To Spike an item, click on the article Action menu and select _Spike Item_. Spiked items can be Unspiked unless they were spiked from a Personal Space.

### Other Useful Features & Tools

#### Templates

Any article can be saved as a Template (a complete copy with all metadata) by clicking on the Action menu at the top of the article editing window and selecting _Save as template_.

There are a few different types of Templates:

* Creation templates: create content with a specific profile.
* Highlights templates: configure certain elements from multiple articles to be displayed as flat/digest files (include headline, abstract, byline, etc.).

New Templates can be created in the _Settings > Templates_ section of the Hamburger menu. Once created, you can generate Highlights daily/weekly/hourly, send out digests listing all items in a Highlight, or schedule Templates to automatically generate articles.

Administrators can set up Templates to be used by all members of a Desk via the _Add New_ button in the Templates tab in Settings. Admins can also edit existing templates.

Templates can be assigned to a Stage and generated at predefined dates and times. When scheduling is turned on, a new item is automatically created and sent to the specified Desk and Stage. Example: schedule a box office report to drop into the working stage at 6am every Monday.

#### Multiedit

The _Multiedit_ button allows you to toggle between multiple open content items, and to display two plain text items side by side in editing mode. Enable Multiedit for an article from the action menu at the top of the article editing window. The Multiedit button appears at the top of the article list. You can select up to 12 articles to open in Multiedit mode at the same time.

#### Highlights

Highlight lists are desk-specific curated lists of important news items. As an editor, Highlights help keep Desk members up-to-date on the day’s top stories. The Highlights icon on the Workspace Panel shows items you've highlighted and Highlights for the current desk. Highlights are used for top-10 lists, section features, and other curated lists. They can be automatically generated against specified metadata, or manually curated. Highlight lists can be published or used internally.

To create a new Highlight:

1. Go to Settings (top-left corner) and select the Highlights tab.
2. Click _CREATE CONFIGURATION_ to make a new Highlight. Highlight lists are desk-specific.

To add a news item to a Highlight list: click the Action menu for the item, choose _Mark item for_, and select the Highlight to which you want to add the item.

#### Versioning

While an item is open for editing, click the _Versioning_ icon on the Editor Sidebar (right-hand side of the article editing window) to display and revert to previous versions. Every time an article is saved, Superdesk retains a copy of the article in its previous form. Reverting to a prior form will not delete the version you reverted from.

The Versioning tab also contains the article history. Click the _Item history_ tab to see who created and updated the article, and which desks and publish queues it was sent to.

### Custom Workspaces and Personal Space

Custom Workspaces are private view configurations accessible from the Desks menu. In Custom Workspaces you can set up widgets and monitoring for your own customized workflow. Unlike Desks (which have a single Dashboard uniform for all users of that desk), your Custom Workspace has its own Dashboard with widgets only you can see.

In your Custom Workspace Monitoring view, select the Desks, Stages and Saved Searches you want to include by selecting the gear icon in the top-right corner. This is useful for monitoring several Desks in a single place.

Personal Space is an icon on the Workspace Panel and is also accessible from the Hamburger menu.

Only you can view or edit items created in your Personal Space. To create a new Personal Item, click the Create icon in the top-right corner of the Personal Space pane.

### Comments

When an article is open for editing, users can add Comments to each news item with Twitter-like @mentions.

This feature is useful for alerting other Desks or users quickly.

This is the Comments button in the Editor Sidebar.

Comments can be viewed in the Editor Sidebar when an article is open for editing, using the Comments button displayed above. Comments can be added to the Body of a news item using the [Inline Comments feature](https://docs.google.com/document/d/1chk8SglS6yZCwqhMLo37mvF5HsZ6iv6Z-x3ASgC4l-0/edit?disco=AAAACmwuhN4\&usp_dm=false\&ts=5caf5429#heading=h.xfv1omnhpquh).

### User Profile Settings

To view and adjust your profile settings, click the User icon in the upper-right corner of the Superdesk interface. Select the _profile_ link under your user name to view profile information. You can set preferences and contact information, view your privileges and view your activity stream.

User privileges are set by administrators via _Hamburger menu > User Management_.

### Suggesting Mode

When a news item is open for editing, you can use the Suggesting feature to collaborate with the article’s author to make changes while preserving the original content. Suggesting mode is available in the full version of editor 3. Older versions of the editor may not have access to Suggesting mode.

To use Suggesting mode, click the Suggesting mode button in the toolbar above the Body HTML textbox.

When Suggesting mode is on, additions are shown in green and deletions are shown in red. [Read more about using Suggesting mode](13-editor-workflow-tools.md#using-the-suggestions-mode).

### Mark for User

As of Superdesk version 1.33, Superdesk includes a _Mark for User_ feature. This allows users to keep track of news items that require their attention. News items can be marked for users in several ways:

* From the action menu of an item in any list view (such as Monitoring or Highlights).
* From the action menu of an item in the Editor or Preview pane.
* Using the icons at the top of the Monitoring pane if multiple items are selected.

Users can access items marked for them directly from the menu to the left of their user icon, or by clicking the _Marked for Me_ button at the top of the Monitoring pane for their current Desk. The info bubble on the _Marked for Me_ button shows how many items have been assigned to you in general, or within your current Desk on the Monitoring pane.

Clicking an item in the _Marked for Me_ list will open it in the Editor, unless the item is locked by another user.

* Spiked items and locked items cannot be marked.
* Only users with the _mark for user_ privilege can use this action.

When marking content for a user, the online status indicator is shown on the user avatars in the list of users, so the marker can see whether the target user is currently online. The marked user will receive a notification in the Superdesk interface and an email notification.

When an item is marked for a user, a new version of the content item is automatically created to ensure the user receives the latest copy and that "dirty changes" are not lost.
