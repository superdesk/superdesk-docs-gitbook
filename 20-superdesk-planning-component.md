# 20 superdesk planning component

The Superdesk Planning Component is an optional module for Superdesk that enables editors and journalists to create a database of upcoming events and plan coverage ahead of time. With the component, editors can assign stories to Desks or to specific users.

The Planning Component can ingest external customer-facing calendars to automatically generate scheduled Events. Assignments integrate with Superdesk workflows to improve internal communication and task completion. External calendar and event metadata can be applied to content produced by journalists, saving time on routine details. Superdesk internal notifications keep users informed, and alerts can be integrated with 3rd-party programs (for example, Slack).

&#x20;Planning icon  Assignments icon

If your organization uses the Superdesk Planning Component, you may see the Planning and Assignments icons in the Workspace Panel. Clicking the Planning icon opens the Planning panel.

In the Planning panel you can create two item types: Events and Planning Items. Create them using the Create icon in the top-right corner of the panel.

* Events — Have a duration and can be recurring or one-time. Events can be ingested from external calendars. Events are not assigned to users; they organize coverage. Once an Event exists, it can be used to generate a Planning Item.
* Planning Items — Used to assign coverage details to your team. Each Planning Item may contain several elements of assigned coverage, each assignable to different users. Planning Items can be exported to generate articles in the Monitoring view. They can also be created independently of Events.

The action menu in the Planning pane allows you to create Agendas and designate Featured Stories. Featured Stories let users curate specific Agenda items to send to Newshub — forming a digest of the day’s most important events. Users can view Featured Stories via a toggle within Newshub.

* Agendas group Planning Items (optional). The Agenda appears in the Planning Item description in the list view.
* Featured Stories appear with a red star in the Planning list view.
* Items with a red stripe on their left margin are locked (only editable by the user who has them opened, unless an admin unlocks them).

When a Planning Item or Event has been posted you will see a green “p” to the left of the item’s slugline. Posted items have been made public. Agendas must be posted to appear in Newshub.

***

## Creating New Planning Items

Click the Create icon in the top-right corner of the Planning pane to create a new Planning Item.

Metadata fields:

* Slugline: Main description for the Planning Item. Appears in bold in the Planning list view.
* Headline: Suggested headline from the creator. When a user starts work, this metadata will populate the new item.
* Name: Name of the user who created the Planning Item (so journalists know who to contact).
* Planning Date (required): Intended creation date for the article. Defaults to current date/time but can be changed.
* Description: Appears in the exported article body and in the Planning list view beside the slugline.
* Internal Note: Internal notes viewable by the user fulfilling an assignment but not shown in the Editor during item creation.
* Agenda: Useful for sorting Planning Items; appears in the Planning list view.

Details section fields:

* Editorial Notes
* Category
* Subject
* Urgency

Coverages:

* After a Planning Item is posted you cannot add additional coverage. To add more, unpost the Planning Item first.
* Click the Create icon to add coverage types. Examples:

When assigning coverage:

* Assign to a Desk and optionally to a specific user within that Desk. If no Desk or coverage is assigned and you export the Planning Item, the article will be created in the most recently assigned Desk.

Click the ASSIGN button in the coverage section to select a Desk and assignee, choose coverage type and due date, then click CREATE to make the Planning Item.

### Adding Coverage to the Assignments tab

Add assigned coverage to the workflow so it is visible in the Assignments tab for the selected Desk or users. Find the coverage in the Planning Item editing pane, then use the action menu at the top of the coverage to select “Add to Workflow.”

Once added to the workflow, the coverage will appear as an assignment in the Assignments tab for the selected user.

***

## Creating New Events

Events are created in the Planning pane via the Create icon. Events organize Planning Items and can be generated manually or ingested from external sources.

Key Event creation fields and controls:

* Repeat toggle: When active, set recurrence (daily, weekly, monthly, yearly, every x days/weeks, etc.).
* Event start / Event end (required): Specify start and end. If All Day is active, times are not required (midnight-to-midnight).
* Timezone: Specify the event timezone (e.g., Asia/Tokyo).
* Slugline: Main description for the Event; appears bold in Planning list view. Searchable via the Planning Advanced Search.
* Event name: Appears beside the Event Slugline in the list view.
* Description: Additional details for the Event.
* Occurrence Status (configurable): Drop-down to indicate likelihood of the Event.
* Calendars (Event Calendars): Controlled vocabularies (Settings/Metadata) to group events (e.g., Sports, Entertainment, Politics).
* Location: Type in the location; use OPENSTREETMAP to search suggestions or use ADD NEW LOCATION to save a commonly used location. The Add New Location pop-up contains fields for location details.
* Contacts: Enter contact details for the Event creator. Use ADD NEW CONTACT if needed.
* Details section: Additional metadata (category, subject, long description, internal note, editorial note).
* Attached files: Attach reference files for journalists/editors.
* External links: Add URLs as references.

### Automatically ingesting external Events

To configure an automatic Event ingest feed:

1. Click Hamburger menu > Settings > Ingest.
2. Click ADD NEW in the top-right corner of the pane.

[Read more about creating an Event ingest feed here.](20-superdesk-planning-component.md#ingesting-news-items-and-events)

### Manually creating Events

Click the Create icon in the top-right corner of the Planning pane and fill in the fields described above.

***

## Events Action menu

Once an Event is created, you can create an associated Planning Item from the Event action menu in the Planning list view.

The action menu for each Event is displayed below:

***

## Export a Planning Item

Export a Planning Item to a Desk’s Monitoring view so journalists can begin work.

{% stepper %}
{% step %}
### Select the Planning Item

Close the Planning Item if it is open, then use the checkbox in the left-most column of the Planning view to select the item.
{% endstep %}

{% step %}
### Export as article

With the checkbox selected, click the EXPORT AS ARTICLE button to send the Planning Item to the Monitoring view.

* If coverage in the Planning Item was assigned to a Desk, the article will be created in that Desk.
* If no coverage was assigned, the article will be created in the most recently assigned Desk.

Alternatively, when coverage is assigned to a specific Desk and user, that user can create the article when they take control of the assignment.
{% endstep %}
{% endstepper %}

***

## Posting Events and Planning Items

Both can be posted to make them visible to subscribers (depending on your setup).

To post:

* Open the item and click the green POST button at the top of the pane.

Once posted, a green “p” appears next to the item in the Planning list view.

When editing a created item you will see options to update or unpost it.

***

## Assignments and Assigned Coverage

When coverage is assigned via the Planning Module, view assigned tasks in the Assignments tab.

The Assignments pane has two views:

* Desk Assignments — varies by the Desk you are viewing. Check the current Desk in the Desks menu (for example, World News Desk).
* My Assignments — coverage assigned directly to you (visible only to you).

Click an item in the Assignments list to reveal options (may vary by permissions and assignment state):

Options:

* Reassign: Send the task to a different Desk or user.
* Edit Priority: Change the assignment urgency.
* Remove Assignment: Permanently delete the task; Planning Item remains with unassigned coverage. Removing an assignment also removes linked assignments. A confirmation pop-up will appear.
* Confirm Availability: Moves the assignment to the Completed section of the Assignments pane.
* Start Working: Prompts to select a template; the item opens in the Editor pane and the assignment status changes to In Progress.

***

If you want, I can convert any long image-heavy sections into expandable blocks or break the page into multiple smaller GitBook pages for easier navigation.
