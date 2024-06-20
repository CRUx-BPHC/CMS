# Changelog

All notable changes to the project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) standards.
Dates are in `yyyy-mm-dd`.

## Unreleased
### Added

### Changed

### Fixed
* Enrolling in an already enrolled course does not give a meaningful error

## Version 1.11 (verCode 1110000), 2024-02-25
### Added
* An icon that displays number of unread notifications
* A new screen to view notifications

### Changed

### Fixed
* HTML Text not rendering properly

## Version 1.10 (verCode 1100000), 2023-05-23
### Added
* Mark All as Read marks notifications as read on website.

### Changed
* Permission request for notification permissions.
* Use full names for courses.

### Fixed
* Cancel button not visible in deletion dialog in dark mode.
* Snackbar message on deletion not properly visible in dark mode.

## Version 1.9 (verCode 1090000), 2021-08-20
### Added
* A new screen to view and delete downloaded files

### Changed
* Login Screen design
* Courses list for a new, modern looking design
* Icons' design

### Fixed
* Profile pictures not fetching properly

## Version 1.8.5 (verCode 1080500), 2021-05-04
### Fixed
* Incorrect theme of system navigation bar
* No refresh indicator when opening notifications

## Version 1.8.4 (verCode 1080400), 2021-03-30
### Fixed
* Crash when downloading discussions
* Crash when enroling to a course

## Version 1.8.3 (verCode 1080300), 2021-03-20
### Fixed
* Overlapping text when viewing big discussions
* App crash when opening certain notifications

## Version 1.8.2 (verCode 1080200), 2021-01-17
### Fixed
* Downloaded files were corrupt
* Could not search for courses in main page

## Version 1.8.1 (verCode 1080100), 2021-01-13
### Fixed
* SSO login for non-admin users
* Course enrolment page does not open

## Version 1.8.0 (verCode 1080000), 2021-01-12
### Changed
* Dark mode is now the default theme 

### Added
* Push notifications

## Version 1.7.1 (verCode 1070100), 2020-11-02
### Changed
* Moodle instance URL

### Fixed
* Unparsed HTML entities in Discussion notifications
* Wrong course name in bottomsheet title
* Unimplemented module types launch module URL in browser
* UI not updating on marking course as read
* Bottomsheet selections not working as intended
* Mark as favorite doesn't update UI

## Version 1.7.0 (verCode 1070003), 2020-10-13

*NOTE: The minimum supported version is now Android 7.0 (API Level 24)*

### Added
* Ability to mark courses as favorite for easier access
* App version and commit hash to 'More Options' in bottom navigation
* Dialogbox on invalid token after Google login
* Notification when logged out while updating course contents in the background

### Changed
* User Interface
* Launcher icon
* Replaced custom Settings activity with Android's Preference Fragment
* Navigation drawer to Bottom Navigation
* Course Content text is now selectable
* Re-download option now rewrites files
* Only Course with Section number shown as title inside course content view

### Fixed
* HTML encoded entities in course names
* Unparsed HTML in notification summary
* Empty ghost site notifications
* Google Login troubles from certain browsers and devices
* Potential infinite loop when resolving files with the same name
* Potential ANR when updating a large number of courses
* Infinite loading animation for modules with SVG icons

## Version 1.7.0-beta.2 (verCode 1070002), 2020-08-20

*NOTE: The minimum supported version is now Android 7.0 (API Level 24)*

### Added
* Add APK version and commit hash to navigation drawer
* Ability to mark courses as favorite for easier access

### Changed
* Launcher icon
* Course Content text is now selectable

### Fixed
* Full Course Names not being displayed (regression in **v1.7.0-beta1**)
* Module Read/Unread Visual Bug (regression in **v1.7.0-beta1**)

## Version 1.7.0-beta.1 (verCode 1070001), 2020-05-09
### Added
* Dialogbox on invalid token after Google login
* Discussion notifications now open up the discussion
* Each screen from the main activity will set its own title

### Changed
* Massive UI changes
* Replaced custom Settings activity with Android's Preference Fragment
* Re-download option rewrites the file
* Replace dialog boxes with bottom sheets
* Show only Course and Section number as title of Course fragment

### Fixed
* HTML encoded entities in course names
* Unparsed HTML in notification summary
* Empty ghost site notifications

## Version 1.6.0 (verCode 1060000), 2019-11-10
### Added
* Google Login
* Ability to share modules without having to download them
* Fragment for Folder Modules
* Notifications for Site News
* File properties in the `More Options` ellipsis

### Changed
* Module names are clickable
* Discussion Attachment names are clickable

### Fixed
* Crash when refreshing discussions and switching to another fragment/activity

### Removed
* Token based login

## Version 1.5.1 (verCode 1050100), 2019-08-15
### Added
* Dark theme for the app, with a toggle in the settings. System preview window will be dark by default.
* Splashscreen for the app
* Ellipsis in course discussions attachments to view, re-download and share downloaded attachment

### Changed
* Change the text of the information in the "About us" section.
* Replace Octocat with the logo of Crux in the "About us" section.

### Fixed
* Repeated notifications of very old forum discussions
* Hyperlinks not clickable in forums posts and course section descriptions #92
* Navigation Bar not updating when back button is pressed
* Unintuitive back button behaviour in the main activity

## Version 1.4.1 (verCode 8), 2018-09-08
### Added
* Notifications for forum posts.
* "Help" button with instructions on logging in using a Token.

### Changed
* `API_URL` from `http` to `https`. This fixes the Cleartext traffic exceptions on Android 9.

### Fixed
* Course names weren't sanitized to proper directory names before passing to `searchFile`, causing a bug where downloaded files couldn't be found.

## Version 1.4.0 (verCode 7), 2018-09-05
### Added
* 'Mark as unread' option for modules in a course
* Notification Channel support for Oreo and above.
* Support for Android Pie (API 28)
* 'Announcements' and other forum modules can now be viewed in-app.
* Custom `TextView` to display HTML content, rather than parsing each time.
* Support for multiple files within a course to have the same file name.
* "Show More/Less" option for longer descriptions.

### Changed
* Swipe to refresh on 'My Courses' syncs changes in all courses. Only refreshed list of courses earlier.
* API served URL changed from "http://id.bits-hyderabad.ac.in/moodle/" to "http://td.bits-hyderabad.ac.in/moodle/"
* Notifications are 'bundled' with a group summary for Android Nougat and above. For lower APIs, each notification is shown separately.
* Refactored `SiteNewsFragment` to `ForumFragment` that supports any forum based on the `forumid` parameter. The older `ForumFragment` is now `DiscussionFragment`.

### Removed
* All usages of `WebView` in the app. All redirects now use the default browser.
* Notification during content sync. `NotificationService` is now used as a proper background service, not as a forground service.

### Fixed
* Notifications not opening the app on being clicked.
* Improper condition while checking if a course is newly added.
* Repeated crashes while syncing updates.
* Bug in SiteNews pagination where only the latest page is displayed and cached.
* Files list for course was being generated using entire CMS directory.
* Added a missing Toast when starting file download from a forum attachment.
