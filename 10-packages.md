# 10 packages

A Package is a container consisting of various news items. You can pair plain text items and image(s) or group several related articles together to be published as one. Packages have their own metadata, independent of the metadata of their individual news items. There are several ways to create and populate a package.

## Creating an empty Package

This is the Create icon.

Users can create a package by clicking the Create icon in the top-right corner of the Monitoring pane.

Clicking the Create icon opens a drop-down menu from which you can select the _Create Package_ option. (Content Profile names in your Superdesk instance may vary from the screenshot.) Packages have their own metadata, independent of the metadata in their individual pieces.

While this empty package is open, you can add news items to it by selecting articles from any article list window (for example the Monitoring pane or Search pane) and clicking the _Add to Current Package_ button at the top of the window.

## Creating a Package from a single item

In the Monitoring or Search tab of the Workspace Panel, choose a news item and click the item’s Action menu icon. From the menu that appears, select _Create Package_.

This creates a package containing the original news item and copies the item’s headline to the package headline.

You can also click the Create Package icon that appears once you select the checkbox beside an item (see Creating a Package from multiple items).

## Creating a Package from multiple items

In any list view (for example the Monitoring or Search tab of the Workspace Panel), select multiple items by hovering over the item’s icon on the left side of the article entry (it turns into a checkbox). Check the boxes for the desired items, then click the Create Package icon in the top-right corner of the window to create a package containing those items.

> Note: If you are creating a package from the Search tab, you cannot use ingested articles to create a package. Articles must be fetched to a Desk before they can be added to a package.

A new package is created with empty metadata but a copy of the headline from the first item you selected.

## Adding items to an existing Package

With a package open, you can add more news items to it.

* To add a single item to an open package: open the item’s Action menu, select _Add to current_, then choose whether it should be featured as main, story, sidebar, or fact box. If you create a package and add items one at a time, the package headline does not get auto-filled.
* To add multiple items: select their checkboxes and click the _Add to Current Package_ icon in the top-right corner.

{% hint style="info" %}
The only reasons an item cannot be added to a package are: it is killed, or it is an ingested item that has not yet been fetched to a Desk.
{% endhint %}

## Packages tab in the Editor sidebar

When an article is open in editing mode, selecting the Packages tab displays whether the article belongs to a package and the name of that package.
