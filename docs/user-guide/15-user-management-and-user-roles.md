# 15 user management and user roles

## User Management and User Roles

The User Management section of the Hamburger menu allows administrators to create new users, disable current users, and edit user profiles.

Admins can access the User Management settings from the Hamburger menu in the top-left corner of the Superdesk interface.

When you open the User Management menu, you will see a complete alphabetical list of all the active Superdesk users for your news organisation. You can search for a specific user using the search bar at the top of the window.

Beside the search icon, there are filters. Toggle between ‘All user types’ or ‘Authors only’ using the blue buttons provided. To the right of those buttons, you will find a drop-down menu that allows you to filter by user status: Choose between Active, Online, Pending, Inactive, Disabled, or All. Pending users are users that have been created within Superdesk, but have not yet confirmed their email to login for the first time.

In the User Management list view, online users are marked with a solid green circle next to their User icon. Admins are marked with a gear icon on the top-left of their User icon. Special notes about inactive or disabled users will appear in pink text next to the user names.

{% hint style="info" %}
Pending users: users created in Superdesk who have not yet confirmed their email to log in for the first time.
{% endhint %}

### Adding New Users

This is the Create icon.

In the top-right corner of the User Management window, you can use the Create icon to add new users to your Superdesk instance. Clicking the Create icon will open a pane on the right where you can input all the information for your new user:

You can change the new user profile picture by clicking on the round grey User icon. You must input all the mandatory fields before you can save the new user profile. In the blank form, mandatory fields are marked by a red asterisk.

{% hint style="warning" %}
Legal usernames can only contain letters and numbers, as well as underscore (\_), apostrophe (‘), dash (-) and period (.). Once the user profile is created, usernames cannot be changed.
{% endhint %}

{% stepper %}
{% step %}
### Create a new user

Click the Create icon in the top-right corner of the User Management window to open the right-side pane for a new user.
{% endstep %}

{% step %}
### Fill in required information

Complete all mandatory fields (marked with a red asterisk). Change the profile picture by clicking the round grey User icon if required.
{% endstep %}

{% step %}
### Save and notify

Click the blue SAVE button at the top of the pane. An email will be sent to the user with instructions to set up their password and login information.
{% endstep %}
{% endstepper %}

***

### Disabling Users and Clearing Sessions

There is a blue toggle at the top of each user profile tab. Switching the toggle to the off position will set the user as **inactive**. This prevents them from logging in to Superdesk. Deactivating a user preserves minimal information (such as their name and username) so you can still search for articles they contributed to and edits they made.

Users can be **disabled** by hovering over the user entry in the User Management list and selecting the trash icon that appears to the right of the user entry. Disabled users will not be able to sign in to Superdesk, but all their profile information is preserved such that they can be reactivated later. This is useful for freelance or seasonally contracted users.

The skull icon that appears in the User Management list view when you hover over a user in the list allows you to **clear all** the user sessions. Clearing all sessions kicks the selected user out of any active sessions; they will need to log in again to continue working.

{% stepper %}
{% step %}
### Make a user inactive

Open the user profile tab and switch the blue toggle to the off position to set the user as inactive (prevents login).
{% endstep %}

{% step %}
### Disable a user

Hover over the user in the list and click the trash icon to disable the user (preserves profile info for reactivation).
{% endstep %}

{% step %}
### Clear user sessions

Hover over the user in the list and click the skull icon to clear all sessions and force re-login.
{% endstep %}
{% endstepper %}

***

### Editing User Profiles

If you have sufficient permissions, clicking an entry in the User Management list opens a preview tab on the right. You can change contact information in the text boxes and click the SAVE button at the top of the user profile tab once changes have been made. Note that usernames cannot be edited.

Changing a user’s role will affect their permissions and privileges. User roles within Superdesk are configurable. Individual permissions can also be adjusted in the full profile view, which you can open by clicking the VIEW FULL PROFILE button at the top of the pane:

Clicking the VIEW FULL PROFILE link opens a new window with the user’s activity stream and where admins can edit specific user permissions by clicking the Privileges tab. The Overview tab displays the same basic information as the preview pane.

<details>

<summary>Overview tab</summary>

The top half of the Overview tab contains basic contact information such as display name, sign-off, email address, and contact phone number. These fields can be edited directly from this tab. Usernames cannot be changed once the account is created.

In the bottom half of the Overview tab you can change your Superdesk display language. This translates the Superdesk UI to your chosen language. You can help translate Superdesk at: https://www.transifex.com/sourcefabric/superdesk/

In the Overview tab you can also reset a user’s login password by clicking the reset password button (admins can use this to reset a user’s password).

Remember to click the blue SAVE button to confirm changes or CANCEL to discard.

</details>

<details>

<summary>Privileges tab</summary>

Admins can adjust individual privileges in the full profile view by clicking the Privileges tab. These checkboxes allow adding or removing specific permissions outside the broad role scope.

</details>

***

### Viewing Your Own Profile Settings

Each user can view and edit their own profile by clicking their user icon in the top-right corner of the Superdesk interface and selecting Profile.

You might see three tabs along the top of your profile: Overview, Preferences and Privileges. The Overview and Privileges tabs are described above. The Personal Preferences tab is accessible only to the account owner.

<details>

<summary>Personal Preferences tab</summary>

In Personal Preferences you can adjust profile defaults and time-saving features.

The first three options let you customize your default view of lists in the Monitoring pane, Archive and Contacts. You can still switch between grid and list view on the actual panes.

Enable or disable email notifications and desktop notifications using the blue toggles. If the toggle is grey (off) you will not receive those notifications.

Article defaults let you pre-populate dateline and place fields for items you create — useful if you report regularly from the same location. These fields remain editable per item.

Preferred categories let you shortlist frequently used categories so you don’t need to scroll through rarely used ones.

Preferred Desks allow you to customize which desks appear first in workflows for sending drafts and publishing.

</details>

***

### Resetting a User’s Password

If a user forgets their Superdesk password, admins can open the user profile tab and click the reset password link to send the user an email with instructions for resetting their password.

***

## User Roles

User Roles are configurable like Desks, Stages, and Content Profiles. The User Roles menu lets you define roles and associated permissions.

Admins can access User Roles from the Hamburger menu in the top-left corner.

The User Roles pane controls access to different functions within Superdesk on a large scale. Individual user privileges can still be edited from each user’s full profile view (see Privileges tab).

From the User Roles panel, rename and change the description of each role by clicking the pencil icon that appears on mouse-over:

Selecting the Set as default checkbox in the Edit Role window will set that role as the default selection when creating new users.

The Roles Privileges pane allows you to choose which roles are eligible for which privileges. Note: the Admin role is not shown here because admins have all permissions by default and this cannot be changed.

Use the checkboxes to add or remove privileges from roles. Users may need to log out and log back in to apply role changes.

***

## Media Contacts

Superdesk includes an internal repository for Media Contacts. Users with appropriate permissions can create and edit these contacts. Media Contacts are accessible through the Hamburger menu:

The Superdesk-internal Media Contacts provide quick access to contact information for media sources, contributors, or subscribers without leaving Superdesk.

New Media Contacts can be added using the Create icon in the top-right corner of the Media Contacts pane. Clicking Create opens a pane on the right:

Required fields are marked with a red asterisk. Click SAVE in the top-right corner to add the contact. In addition to phone and email, you can add fax, Twitter, Facebook, Instagram, and street address.

In the Media Contacts pane, clicking the mail, Twitter, Facebook, or Instagram icons will open those websites or your computer’s mail program.
