+++
author = "RsyncOSX"
date = "2020-04-02"
title =  "The RsyncGUI changelog"
tags = ["rsyncgui"]
categories = ["changelog"]
description = "Changelog"
lastmod = "2021-01-24"
+++
RsyncGUI is a sandboxed macOS app compiled with support for macOS 10.15 Catalina and 11.01 Big Sur. The application is implemented in Swift 5 by using Xcode 12. Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncGUI (and rsync) at any time and still have access to all synchronized files.

The [App Sandboxing technology](https://developer.apple.com/app-sandboxing/) is a technology for protecting the user for malicious software. To release a macOS app on Apple Mac App Store require the app to execute inside a sandbox. RsyncGUI is an adapted version of [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX) to execute inside a sandbox. There are a few limitations compared to RsyncOSX.

## Some words about RsyncGUI

The UI of RsyncGUI can for users who dont know rsync, be difficult or complex to understand. Using RsyncGUI requires some knowledge of `rsync`. The main objective for RsyncGUI is to ease the use of `rsync`, not teach macOS users how to use `rsync`. That is beyond the scope of RsyncGUI. Setting the wrong parameters to rsync can result in deleted data. And RsyncGUI will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.


### RsyncGUI as your main tool for backup

If your plan is to use RsyncGUI as your main tool for backup of files, please investigate and understand the limits of it. RsyncGUI is quite powerful, but it is might not the primary backup tool for the average user of macOS.

### The --delete parameter

Caution about RsyncGUI and the `--delete` parameter. The parameter is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncGUI, execute an estimation run (`--dry-run`) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncGUI (rsync) will delete all files in the destination.

## Old version of rsync

The default version of rsync in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version 2.6.9 was released in nov 2006. The current release of rsync is version [3.2.3](https://download.samba.org/pub/rsync/NEWS) protocol 31. Utilizing snapshots in RsyncGUI is not possible due a bug in default version version 2.6.9 of rsync. It is not allowed because of the macOS sandbox, to execute an updated version of rsync in e.g /usr/local/bin. Utilizing scheduled task is also not implemented in RsyncGUI.

If you need either of them, please use [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX).

## Version 2.3.6

This version is approved for release on Apple Mac Store 17 January 2021.

The following is changed:

- this is a maintenance release

## Version 2.3.5

There are several internal changes in this release. The following are changes:

- application icon updated for Big Sur, by [Zsolt Sándor](https://github.com/graphis)
- and several internal changes
- fixed wrong actions in Toolbar

## Version 2.3.3

This version is approved for release on Apple Mac Store 7 December 2020.

There are several internal changes in this version (refactor of code) to make the maintenance of the code more easy.

- the main view is cleaned up and there is a new menubar on left side with the main actions for each view
- there are two new actions in main view, select a task and slide to left to execute, slide to right for delete
- the restore function is changed as well, there is now only possible to do restore, either full or file by file, to a temporary restore path
- there are fixed some minor bugs in the abort functions

## Version 2.3.2

This version is approved for release on Apple Mac Store 29 November 2020.

There is fixed a minor issues utilizing the shortcuts like copy (`⌘C`) and paste(`⌘V`) values from commandline into like the Add configurations. And there is a cleanup within the `Assist` function as well.

There are several internal changes in this release (refactor of code) to make the maintenance of the code more easy.

## Version 2.3.0

This version is approved for release on Apple Mac Store 13 November 2020.

## Version 2.2.9

This version is approved for release on Apple Mac Store 10 November 2020.

- maintenance release and some refactor of code
- added backup of configurations

## Version 2.2.5

This version is approved for release on Apple Mac Store 27 September 2020.

- maintenance release and bugfixes
- several internal changes
- the restore part is adjusted

## Version 2.2.0

This version is approved for release on Apple Mac Store 24 August 2020.

- maintenance release and bugfixes

## Version 2.1.9

This version is approved for release on Apple Mac Store 26 July 2020.

- maintenance release and bugfixes

## Version 2.1.6

This version is approved for release on Apple Mac Store 14 June 2020.

- fixed a bug in the Sequrity Scoped part of RsyncGUI

## Version 2.1.5

This version is approved for release on Apple Mac Store 12 June 2020.

The ssh part of RsynGUI is changed, [see ssh](/post/ssh/).

- the user can add a user selected ssh keypath and identityfile
- RsyncGUI can assist in creating rsa based ssh keypair

## Version 2.1.1

This version is approved for release on Apple Mac Store 17 May 2020.

- added counting numbers in quick backup
- added clean logfile in view output from rsync
- some minor fixes and cleanups


## Version 2.1.0

This version is approved for release on Apple Mac Store 4 May 2020.

- some minor bugfixes
- refactor of restore
- copy and paste output from rsync to macOS clipboard
- view logfile in view for rsync output

## Version 2.0.1

This version is approved for release on Apple Mac Store 15 April 2020.

- fixed a bug in abort task

## Version 2.0.0

This version is approved for release on Apple Mac Store 26 March 2020.

- batch is replaced with multiple selection of rows for executing
- minor GUI tweaks and cleanup

## Version 1.9.1

This version is approved for release on Apple Mac Store 27 February 2020.

- a few minor fixes

## Version 1.9.0

This version is approved for release on Apple Mac Store 18 February 2020.

- redesign of the Restore view
- some bugfixes

## Version 1.8.9

This version is approved for release on Apple Mac Store 28 January 2020.

- a few enhancements and fixes
- select other profile from Synchronize view

## Version 1.8.5

This version is approved for release on Apple Mac Store 22 December 2019.

- a few bugfixes
- cleanup of GUI
- new task syncremote which synchronize a remote source to local storage on Mac, the task require a remote server

## Version 1.8.1

This version is approved for release on Apple Mac Store 9 November 2019.

- a few internal updates and fixes

## Version 1.8.0

This version is approved for release on Apple Mac Store 24 October 2019.

- updated restore function
- refactor and cleanup in code
- fixed a couple of bugs

## Version 1.7.2

This version is approved for release on Apple Mac Store 7 September 2019.

- a few bugfixes

## Version 1.7.0

This version is approved for release on Apple Mac Store 29 August 2019.

The major part in this version are refactor and cleanup in code. Refactor is mainly for decoupling of code and make RsyncGUI easier for maintenance. I am also deleting not used code. The command wc  -l *.swift in the source catalog of RsyncGUI counts number of lines and swift classes and structs. There are about 200 classes and 12,600 lines of code in RsyncGUI now.

- fixed a couple of memory leaks
- a few GUI adjustments
- fixed a bug in delete logs and save logs to permanent store
- some adjustments in search and sort (in logs and all profiles)
- refactor of code and cleanup

## Version 1.6.0

This version is approved for release on Apple Mac Store 2 August 2019.

- some GUI adjustments
- fixed a bug in delete logs and save logs to permanent store
- some adjustments in search and sort (in logs and all profiles)

## Version 1.5.0

This version is approved for release on Apple Mac Store 27 June 2019.

- fixed some memory leaks
- this is primary a maintenance release, fixed some bugs and cleanup in code

## Version 1.1.0

This version is approved for release on Apple Mac Store 4 April 2019.

- quit RsyncGUI by red button upper left main window
- RsyncGUI center itself in screen when started
- view all profiles and configurations by menu button (moved from tab view)
- backup now and automatic backup my be executed from any view (tab) by menu buttons or shortcuts
- clean up of code and some bugfixes
- configuration is available by shortcut ⌘, (Preferences)
- built by last release of Xcode 10.2
- removed code for snapshots (due to stock version of rsync in macOS)

## Version 1.0.1

Version 1.0.1 is released 4 February 2019. Some minor bugfixes after initial release.

## Version 1.0.0

The app is [released](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store 24 January 2019.
