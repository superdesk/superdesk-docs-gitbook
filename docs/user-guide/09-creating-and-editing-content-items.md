# 09 creating and editing content items

This is the Create icon.

On your Dashboard the Create icon allows you to add widgets. On the Monitoring tab, or in your Personal Space, the Create icon allows you to make new articles, new packages or upload audio, pictures, and video from your computer into Superdesk. On the Dashboard tab, the Create icon only allows you to add widgets to your Dashboard. In versions of Superdesk 1.33 and later, you will also find the option to create new content items using the new icon in the bottom right of the Superdesk interface.

This upgrade allows you to create new content items in all panes, not just the Monitoring tab.

## Making New Articles

To start writing a news item or uploading media, click the Create icon in the top right corner of the Monitoring Pane or Personal Space. In versions after 1.33, you can also create items via the bottom-right Create icon regardless of pane. Clicking the Create icon opens a menu:

{% stepper %}
{% step %}
### Choose how to create

* CREATE NEW ITEM — Select a Content Profile for the new item (e.g., “Plain Text”). Content Profile names depend on your settings.
* RECENT TEMPLATES — Choose a template pre-filled with metadata. Frequently used templates appear here.
* CREATE PACKAGE — Make a new, empty package (a grouping of related news items).
* UPLOAD MEDIA — Upload media from your computer into Superdesk.
{% endstep %}

{% step %}
### Opened editor pane

When you choose to create a new item, a new pane opens on the right side of the Superdesk interface. Depending on the Content Profile you'll see metadata fields such as Slugline, Genre, Place, Headline and Body (BodyHTML is where you create the main article text).
{% endstep %}

{% step %}
### Edit body text and format

When typing in the Body HTML box you will see a blue toolbar above the textbox for formatting. The toolbar includes (icons shown in UI):

* Headings
* Block quote
* Bulleted list
* Numbered list
* Paste with formatting
* Bold
* Italic
* Underline
* Strikethrough
* Superscript
* Subscript
* Add link / attachment
* Embed
* Add media into body
* Insert table (with table editing options)
* Remove formatting
* Inline Comments
* Annotations
* Suggestions Mode toggle
* Show invisible formatting (e.g., line breaks)

If your editor version lacks the remove-formatting button, remove formatting by toggling the same formatting button you used to add it (e.g., deselect the quote button to remove quotes).

Superdesk displays word and character count above the main body text box.
{% endstep %}
{% endstepper %}

### Using the Suggestions Mode

{% stepper %}
{% step %}
Toggle Suggestions Mode with the button above the Body HTML field.
{% endstep %}

{% step %}
When active (blue):

* Added text appears in green.
* Deleted text appears in red with strikethrough.
* Formatting changes are highlighted in green.
{% endstep %}

{% step %}
To accept or reject changes, click the altered text and choose “accept” or “reject” in the pop-up. This supports collaborative editing while preserving the original text.
{% endstep %}
{% endstepper %}

### Using the Annotations feature

The Annotations feature adds contextual notes to parts of the article body. Annotated text is underlined in green.

{% stepper %}
{% step %}
To create an annotation in the article editor:

1. Highlight text in the Body HTML field.
2. Click the Annotations button in the toolbar.
{% endstep %}

{% step %}
A pop-up appears with two halves: New Annotation and Annotations Library. Choose an Annotation Type and add the Annotation Body. Submit to create the annotation.

Options in the Annotations Library show previously used annotations relevant to the highlighted text.
{% endstep %}

{% step %}
To view or manage annotations:

* Click any underlined-in-green text to view the annotation.
* Use the action button in the annotation pop-up to edit or delete it.
{% endstep %}
{% endstepper %}

#### Annotations Library

Annotations can be created and managed from the Annotations Library in the Hamburger menu.

To create a new annotation in the library:

* Click Create (top right).
* Provide Name, Language (language code), and Definition. All fields are mandatory.
* As of Superdesk 1.33, multiple annotations can share the same name; Language defaults to a prefilled value but can be changed.

Saved annotations become available in the Annotations Library tab of the article annotation pop-up. An annotation shows up in the list only if the highlighted text exactly matches the annotation Name.

### Using the Inline Comments feature

{% stepper %}
{% step %}
Add an Inline Comment:

1. Highlight text in the Body HTML field.
2. Click the Comments button in the toolbar.
3. Type your comment in the pop-up and click SUBMIT. Use @username to notify a user.
{% endstep %}

{% step %}
View and manage Inline Comments:

* Open the Editor Sidebar and select the Inline Comments tab to see all inline comments (resolved and unresolved).
* Use the RESOLVE button on a comment or reply in the textbox to resolve it.
{% endstep %}
{% endstepper %}

### Adding Media to the Body of your Article

{% stepper %}
{% step %}
Insert media into the body:

* Click the media icon in the toolbar above the Body HTML field.
* Choose files to upload from your computer (multiple selection supported).
{% endstep %}

{% step %}
Add metadata and upload:

* You may be prompted to enter title, description or headline for each media item (required fields marked with a red star).
* Use SELECT ALL to apply metadata to all selected files, or edit each individually.
* Click Upload, then edit the media (rotate, crop, adjust brightness, contrast, saturation).
* Click DONE to insert the media into the article.
{% endstep %}

{% step %}
Edit inserted media:

* Click the inserted photo in the editor to open the image editor.
* Top buttons: Details / Metadata, Edit Image, Edit Crops.
* Edit Image options: crop, rotate left/right, flip vertical/horizontal, adjust brightness/contrast/saturation.
* Edit Crops: choose predefined sizes and adjust area of interest using crosshairs.
* Remove an image by clicking the “x” shown when hovering over it.
{% endstep %}
{% endstepper %}

The media upload supports photos, audio and video where publishing destinations accept them.

## Creating Packages

Packages group related news items. There are multiple ways to create a package.

{% stepper %}
{% step %}
Create an empty package:

* Use the Create icon in the top-right of the Monitoring Pane (or Custom Workspace).
* This creates an empty package; add package-level metadata in the header. Packages store their own metadata independent of individual items.
{% endstep %}

{% step %}
Add existing articles to an open package:

* From Search or Monitoring tabs, hover over items to show checkboxes.
* Select articles and click Add to Current Package (top-right).
{% endstep %}

{% step %}
Create a package with selected content:

* Select items and click Create Package (left of Add to Current Package).
* A create-package window opens with selected articles attached; enter package metadata and save.

Note: Packages cannot be created from the Personal Items tab (Personal Space).
{% endstep %}
{% endstepper %}

See the Packaging section in the Superdesk Manual for more ways to create packages: [Packages](09-creating-and-editing-content-items.md#packages).

## Moving Items between Desks and Stages

This is the Send To button.

{% stepper %}
{% step %}
If you created an article in Personal Space and want others to review it, open the article and click Send To (top-right) to send it to a Desk.
{% endstep %}

{% step %}
Depending on permissions, Send To can also submit the item for publishing. If not ready, click SAVE then CLOSE to revisit later.
{% endstep %}
{% endstepper %}

## Editing and Re-opening Existing Items

Item list views appear in the Monitoring pane, Search pane, or Personal Space. Hovering over an item reveals an Action menu on the right.

To continue writing:

* Hover over the item, open the Action menu and select Edit. Available actions depend on the item status, your permissions, and installed components (e.g., planning).

### Top editing-window tools

Along the top of the editing window you’ll find:

* Minimize — first button: minimizes the article and creates a shortcut in the Workspace Bar.
* Action menu — second icon: options include saving the formatting as a template, opening Multiedit side-by-side editing, running spell check, etc. Dictionaries can be set in Settings > Hamburger menu.
  * Multiedit can be activated from this menu or from the Monitoring tab by selecting multiple articles and clicking Multiedit.
* Send To — third icon: send the article to a Desk, Stage or publish (depending on permissions).

## Editor Sidebar

The Editor Sidebar provides additional options for items opened for editing. Tabs shown depend on the Content Profile in use. When a tab is open its icon is blue; hover to reveal an “x” to close the tab.

### Info Button (Metadata)

The first button below Send To is the Info button. The Info/Metadata tab lets you add/view metadata, expiry, unique name and more.

Metadata fields commonly include:

* Not for Publication: a toggle that marks the article; it does not prevent publishing but flags it in lists.
* Legal: flag indicating legally sensitive content (does not block publishing).
* Usage terms: notes about publishing conditions (may be inherited from ingest).
* Language: language code (may determine dictionary).
* PubStatus: Usable or Unusable.
* State: article status flags (legal, fetched, not for publication, takes, corrected, published, etc.).
* Expiry: optional auto-expiry info (expired items are deleted and cannot be edited/published).
* GuID: unique global identifier (cannot be changed).
* Unique Name: editable identifier for easier searching (searchable in Advanced Search).

Note: Not for Publication toggled on marks the item but does not prevent publication.

The Info tab also shows version, source, urgency, genre, type and last-updated details.

### Find and Replace

Use Find and Replace to locate and update words/phrases.

* Type the word to find in FIND and the replacement in REPLACE WITH.
* Use REPLACE to change occurrences one at a time, or REPLACE ALL to change them all.

### Comments (general)

The Comments tab is for general discussion about the item (different from Inline Comments). New comments appear in an info bubble; add a new comment at the bottom and click POST.

### Versioning

Every save (including autosave after 3 seconds of inactivity) creates a version stored in Versions tab. Access previous versions and click REVERT to continue from a previous version while preserving all versions. Item History shows who created/updated the item and when.

### Packages Info

Packages tab shows whether the open item is part of any packages. It lists package headlines with the date/time the item was added; clicking the package opens or allows editing it (with appropriate permissions).

### Macros

View and apply macros (created in the backend) from the Macros tab. Macros can be grouped to make them easier to find.

### Attachments

The Attachments tab lets you add and view files attached to the news item.

* Click ATTACH FILES to upload attachments. The Attach Files pane lets you select files and set whether attachments are internal or published with the news item using a toggle.
* Add title and description as required. File size restrictions may apply depending on settings.

### Inline Comments (Editor Sidebar)

The Inline Comments tab displays inline comments submitted for the item. Inline comments are not transmitted on publication but remain associated with the article through workflows.

To add inline comments: highlight text in the Body HTML field, click the Comments icon in the toolbar above the text box, enter a comment and click SUBMIT. Use @username to notify specific users. Comments are for internal workflow; use the Editor’s notes in the metadata header for information that should be transmitted with the content.

(See Using the Inline Comments feature above for more detail.)

### Related Items

The Related Items tab shows items that share the same slugline or configured fields. While editing text items (not packages or media) you can search to find related items and relate them together.

From the Related Items tab’s action menu you can open an item, associate metadata or mark an item as an update. The gear icon allows configuration of complete/partial slugline matches and recency limits.

If an item in Related Items is locked, that status is shown in the pane.
