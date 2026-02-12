# 17 content configuration

The Superdesk Hamburger menu is where most of the newsroom workflow is set up. In the Admin tools section, under the Settings heading you can create Desks and Stages, manage Content Profiles, create Highlight lists, set default user privilege profiles, edit Subscribers, create Templates and more.

There are three sections within the Settings area: Content Flow, Workflow, and Content Configuration.

* The Content Flow section contains settings pertaining to how news items move from Superdesk to your customers or other Superdesk-internal locations (Internal Destinations). You will find the features in this section described in the Superdesk [Publishing chapter](17-content-configuration.md#steps-to-publishing-in-superdesk).
* The Workflow section contains settings pertaining to [user roles,](17-content-configuration.md#user-roles) [desk creation and desk stages](17-content-configuration.md#desk-creation-and-desk-management).
* The Content Configuration section contains settings pertaining to metadata fields for new item creation, highlight creation, templates and vocabularies. The content configuration section of the Settings menu is described below:

## Content Profiles

Content Profiles are used to define metadata for new item creation. Content Profiles determine which fields are available, and which fields are required when a news item is created.

To get started with Content Profile creation, click the Hamburger menu, then select Settings > Content Profiles.

Admins can create new Content Profile templates by clicking on the +ADD NEW button at the top right of the Content Profiles tab.

{% stepper %}
{% step %}
### Create a new Content Profile — Step 1: Name & description

* Assign a name and a description for the new Content Profile.
* Press the SAVE & CONTINUE button to proceed to metadata and fields customization.
{% endstep %}

{% step %}
### Create a new Content Profile — Step 2: Configure fields

In the Edit Content Profile window you will see three tabs:

* Header Fields: fields that are not transmitted to readers (used for Superdesk-internal communication).
* Content Fields: fields that are transmitted to readers.
* Widgets: dictates which items are present in the Editor Sidebar of the article creation window.
* Mark a field mandatory by clicking the ‘Required’ checkbox.
* For most text fields, specify minimum and maximum character length where available.
* Use the Create icon above or below each field to add additional fields.
* Custom fields can be configured via Hamburger menu > Settings > Metadata.
{% endstep %}
{% endstepper %}

## Dictionaries

The Dictionaries tab allows you to select which dictionary Superdesk will use for internal spell check. Superdesk supports multiple dictionaries for spell checking. Superdesk can also be integrated with 3rd party tools such as [Tansa](https://www.tansa.com/).

To configure a Superdesk-internal Spell Checker, select Hamburger menu > Settings > Dictionaries.

Click the Create icon in the top-right corner of the Dictionary Management pane to add a global dictionary, a personal dictionary, or an abbreviations dictionary.

In the Add New Dictionary window you must add a unique name and ISO language code. You can [check a list of language codes](http://www.lingoes.net/en/translator/langcode.htm) if needed. Any global or personal dictionary will also require uploading a reference file. Dictionary files must be in .txt format, with one entry per line.

* Personal dictionaries are only available to the user that creates them; global dictionaries are available to all Superdesk users in your organization.
* Once created, you may need to log out and log back in to begin using the new dictionary.
* Set the dictionary to active using the toggle at the top of the dictionary configuration window.
* Multiple dictionaries with the same language code are supported (for example, a medical dictionary and a general one). Superdesk uses all active dictionaries that match the news item’s language code concurrently.
* View a news item’s current language code using the information button in the Editor Sidebar when editing an article.

#### Adding additional entries to a Dictionary

{% stepper %}
{% step %}
### Add entries via Dictionary Management

1. Go to Hamburger Menu > Settings > Dictionaries.
2. Select the edit icon when hovering over the Dictionary you want to add entries to.
3. In the Edit Dictionary window, search the Dictionary using the search textbox at the bottom.
{% endstep %}

{% step %}
### Add or remove words

* If the word is not in the Dictionary, use the ADD WORD button beside the search textbox.
* Entries can also be added from the article editing window; in that case the word will be added to the user’s personal dictionary.
* To delete an entry, use the trash icon beside the searched entry to remove it.
{% endstep %}
{% endstepper %}

#### Using the Spell Check feature

* Once Dictionaries are configured, use the spell check by selecting the action menu in the top-right corner of an article open for editing.
* If the Run Automatically toggle is on (blue), it checks words as you type; otherwise run Spell Check manually (ctrl + shift + y).
* The Spell Check scans the Headline, Body and Abstract fields for spelling errors.

### Abbreviations Dictionary

The abbreviations dictionary is a personal dictionary tool that enables automatic text expansion while writing articles.

To set up your abbreviations dictionary:

{% stepper %}
{% step %}
### Create an Abbreviations Dictionary

* Go to Hamburger Menu > Settings > Dictionaries.
* Click the Create icon in the top-right corner of the dictionary management pane, then select Abbreviations Dictionary.
* In the "Add New Abbreviations Dictionary" window, enter a language code (for example: EN for English) so the abbreviation dictionary can be bound to articles of a certain language.
{% endstep %}

{% step %}
### Add abbreviations

* Enter the abbreviation to be replaced (for example: UN).
* Enter the phrase to replace it with (for example: United Nations).
* Click ADD ABBREVIATION. The new abbreviation appears below the button.
* Add further abbreviations or click Save to close the window.

Example: typing UN\* in a body text and hitting space will replace it with United Nations.
{% endstep %}

{% step %}
### Edit existing abbreviations

* Once a dictionary exists, edit it from the Dictionary Management section by clicking the pencil icon beside the dictionary you wish to edit.
* Editing an abbreviations dictionary here lets you add more items.

You only need to click the Create icon the first time you add a dictionary.
{% endstep %}
{% endstepper %}

## Highlights

Highlights allows creation and configuration of Highlight lists — desk-specific curated lists of news items used for top-10 lists, section features, and other curated lists. Highlights can be automatically generated using metadata or curated manually. Highlight lists can be published or used internally.

New Highlight lists can only be created from Hamburger menu > Settings > Highlights.

To create a new Highlight, click the CREATE CONFIGURATION button in the upper-right corner of the Highlights Configurations window. This opens options for creating a new Highlight list.

* CONFIGURATION NAME: name the Highlight.
* TEMPLATE: choose the template applied when a new article is added to this Highlight.
* ASSIGNED DESKS: desks that can view the Highlight; these are desks that items are automatically added from upon creation of the Highlight.
* AUTOMATICALLY INSERT ITEMS: choose the timeframe in which items are automatically added to the Highlight upon creation (for example, items from the last 12 hours). If no desk is selected on creation, the Highlight is entirely curated manually and will be available to all desks; users with appropriate privileges can add content manually.

## Metadata

Most fields in Superdesk are configurable to meet organizational needs. The Metadata section allows you to define fields for news item creation, media contacts, events and planning, etc.

To start defining metadata fields, select Hamburger menu > Settings > Metadata.

At the top of the Metadata Management pane, you may see tabs such as Vocabularies and Custom Text fields. Previously defined entries appear in the pane; the grey number bubble beside an entry indicates how many defined options it contains.

To define a new field, click the +ADD NEW button in the top-right corner.

When creating or editing a metadata field, the available properties include:

* ID
* NAME: the title of the metadata field as it appears in Superdesk.
* DESCRIPTION: internal description visible in the metadata management pane.
* CATEGORY: used to organize the Vocabulary list.
* WIDTH: size of the field in pixels.
* HELPER TEXT: explainer text for fields in the Editor (appears for content fields of a content profile).
* SHOW TO USERS AS: choose single selection, multi-selection or neither.
* ITEMS: for fields with multiple values, enter selectable values using the +ADD ITEM button.

## Search Providers

The Search Providers tab enables administrators to set up external content providers (for external image searches, for example).

Click the +ADD NEW button in the upper-right corner of the Search Providers window to add a new Search Provider.

In the Add New Search Provider window you can:

* Toggle the Search Provider on or off.
* Select the provider type and enter the source name.
* Enter username and password credentials required to configure the Search Provider functionality.

## Templates

The Templates pane displays all current Templates for your Superdesk instance. Templates are Content Profiles with metadata fields already filled in. Uses include saving time in routine news item creation, auto-generating articles, generic kill notifications for subscribers, or auto-formatting items in a Highlight List.

Click the Create icon in the top-right corner of the Templates pane to create a new Template. Each created Template appears in a box showing the template type, assigned Desk and Stage (if any), and automated item creation schedule (if any).

* Use the Action menu on a Template to Edit or Remove it.

Within the Edit Template window you can enter or update Template information.

{% stepper %}
{% step %}
### Template: left side — basic settings

* Add a name for the Template.
* Set the Make Public toggle on (blue) so users other than the creator can use the template; in the off position the Template is personal.
* Choose a Content Profile from the drop-down menu. The selected Content Profile determines which metadata fields appear below the Make Public toggle.
* Choose the Template Type (Create or Highlight).
{% endstep %}

{% step %}
### Template: left side — content fields

* Fill in content fields shown in the bottom half of the left-side window. Any information entered here will appear in every news item created using this Template. The fields depend on the selected Content Profile.
{% endstep %}

{% step %}
### Template: right side — desks & metadata

* If the Template is public, expand the Desks tab to select desks that will have access to the Template (blue = access).
* Expand the metadata tab to edit other Template settings such as Language, Not for publication toggle, target regions, etc.
{% endstep %}

{% step %}
### Template: scheduling & save

* The AUTOMATICALLY CREATE ITEM toggle (when set to on) expands scheduling options. Automatically created items will appear in the assigned Desk stage at chosen times (useful for recurrent weekly news items).
* Click SAVE at the bottom of the window to create your Template.
{% endstep %}
{% endstepper %}
