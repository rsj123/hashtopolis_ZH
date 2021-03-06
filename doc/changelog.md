# v0.7.1 -> v0.8.0

## Features

- The server can store sent debug output from Hashcat sent by the agent.
- Files now also are associated to an Access Group to control the visibility of files.
- Agent data about device temperature and util is collected and can be viewed on the server.
- Notes can be added to tasks
- Static chunking (if for some reasone a fixed number of chunks or static chunk size should be used for a task)
- The server can provide a list of deleted filenames to the agent when he asks for.
- Tasks can now be copied to preconfigured tasks and preconfigured tasks can also be copied to preconfigured tasks.
- A test framework was added to run automated tests on Travis.
- To make sure rules are applied before rejecting, piping can be enforced.
- Added Notification type for Slack.

## Enhancements

- Task attack commands can be changed after creation, e.g. to fix typos
- Switch between tasks and archived ones is easier
- Archived tasks can be deleted at once
- Task priority can now be set directly in the task creation form.

## Bugfixes

- New task creation page now also shows the other file type.
- New file creation with the user API now takes the right file type.
- Vouchers are tested for uniqueness on creation to avoid duplicated ones.
- Disabling rule splitting when having a prince task.
- Fixed non-working secret checkbox for hashlists.

# v0.7.0 -> v0.7.1

## Bugfixes

- Fixed permission check for file downloads with URLs from the user API
- Fixed issue with creating supertasks from preconfigured task list
- Fixed creation of tasks from preconfigured tasks out of the hashlist view
- Fixed mask import
- Fixed hiding of mask imports in preconfigured task list on hashlist page

# v0.6.0 -> v0.7.0

## Features

- Tasks which are recognized containing large rule files and not giving good benchmarks result in splitting into subtasks
- Most of the tables can now be easily ordered and searched with the datatables plugin
- Agent Errors can be handled better
- New User API allowing access to all functions without the webinterface via simple JSON commands.
- Added new filetype (Other) for all non rules/wordlist files like hashcat charsets etc.
- File types can be edited of existing files.
- Tasks can now be archived instead of being deleted.

## Enhancements

- Width of the container is increased to have more space on large screens.
- Standard buttons have now icons instead of text to use less space.
- Hashcat is configured already as crack to make it easier for users to get started.

## Bugfixes

- Using correct function to get superhashlistId on zapping from webinterface.
- Zapping from the website will now also issue zaps for non-salted hashlists.
- Fixed zapping querying on progress sending from agent to also match for agent null values.

# v0.5.1 -> v0.6.0

## Features

- Added autofocus for login field
- Added fine grained permission management
- Updated Bootstrap and jQuery to newest versions
- Added Icons instead of images

## Bugfixes

- Export of founds of binary hashlists fixed
- DB Connection check during installation is now tested correctly

# v0.5.0 -> v0.5.1

## Bugfixes

- Fixed missing file assignments when applying preconfigured tasks from hashlists view (issue #354)
- Fixed cracker binary relation error when applying supertasks from hashlist view
- Fixed XSS vulnerability with the login forward variable
- Session cookies have the httpOnly flag set
- Fixed file upload which allowed upload of file:// data and reading it
- Fixed renaming of files which allowed renaming them to other directories and execute them
- Fixed renaming/uploading of files which allowed to override hidden files (e.g. .htaccess file)

# v0.4.3 -> v0.5.0

## Large Update

- Complete task management backend rewritten
- Improved performance when handling cracked hashes
- Added Groups for more detailed access control
- Including new python client
- Compatibility with generic crackers
- More configuration options added
- Cracker version management changed

## New Features

- Tasks now have a cracks per minute performance based on total spent time

## Bugfixes

- Fixed dependency problem on user deletion
- Fixed issue when agents got deleted which had completed at least one chunk
- Fixed conflicts on $_POST data agent vs. agentId
- Fixed ETA and spent time for tasks
- Error message which was always shown when adding new hash types fixed

# v0.4.2 -> v0.4.3

## New Features

- Added telegram bot notification
- Supertasks can now also be applied when viewing hashlist details (similar to preconfigured tasks)

## Bugfixes

- Notification display fixed
- Updated problem where agents were looping when tasks go over 100%

## Technical

- Fixed warnings during found import
- Fixed edge case where it could happen that agents started to loop after a task when no new task was available
- Pre-crack import warns when too long plaintexts are in the import file
- Implemented missing ownAgentError notification execution

# v0.4.1 -> v0.4.2

## New Features

- Supertask imports can now be set to be small tasks for every subtask

## Bugfixes

- Fixed broken agent download

## Technical

- Typos in constants fixed
- Tasks can also be deleted from the detailed view
- Fixed update to 0.4.0 when adding taskType column
- Supertasks are getting default priority from the subtasks
- Fixed DBA issue with handling invalid input
- Fixed additional vulnerabilities reported
- Fixed remaining fragments when deleting finished supertasks

# v0.4.0 -> v0.4.1

## Bugfixes

- Various vulnerabilities (CVE-2017-11680, CVE-2017-11681, CVE-2017-11682) fixed, see [issue #241](https://github.com/s3inlc/hashtopolis/issues/241)

## Technical

- Improved code handling, constants can be used in templates.

# v0.3.2 -> v0.4.0

## New Features

- Renewed status page, gives now JSON formatted information which can be parsed however the user wants to.
- added search page to search for hashes and plains
- '-r' is now automatically prepended when selecting rule files on task creation
- added help page with some helpful links
- Left hashlists can be downloaded now
- Added Yubikey OTP login
- Supertasks added
- HCmask style can be imported

## Technical

- DB connection details now are stored in a file which is not in repository (a template is provided instead). This avoids conflicts on updates in `inc/load.php`
- Hash length is increased to 1024 (old 512)
- Added special case when handling pre-crack import of WPA as they are not matched via the hash but the ESSID instead.
- Added new hashtypes from Hashcat
- Server hostname can be overridden in config

## Client

- Client updated to version 0.43.19 
- Fixed debug not showing hashcat parameters on calls
- Improve error handling on keyspace measuring, client will now signal the server to pause agent instead of crash
- Added more information for task assigning, client will now display task and hashlist on task get
- Fixed slow file downloading issue
- Changed the way hashcat version is queried (should work properly on linux/mac)

# v0.3.1 -> v0.3.2

## Client

- Client updated to version 0.43.13

## Bugfixes

- fixed not sending notifications when using pre-task creation from hashlist details view
- 'Delete Finished' button now deletes also tasks of hashlists which are completely cracked
- on user deletion depending sessions now also get deleted
- fixed problems on task assignment where priorities were compared wrong
- clear all doesn't fail anymore when task list is empty
- fixed problem that on small tasks multiple agents got assigned and assignments were deleted immediately
- fixed issue that some agents suddenly got a very large chunk

## Features

- Added possibility to change isCpuOnly and isSmall on tasks after creation
- DB details are now saved separately to the other loading part, so conflicts on updates are avoided

## Technical

- removed old installation code which was used to upgrade Hashtopus to Hashtopolis 0.1.0
- reduced size of task progress image

