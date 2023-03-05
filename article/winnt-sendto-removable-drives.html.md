---
title: 'Remove drive-letters for removable drives from Send-To'
date: '2007-07-02T07:44:43+02:00'
status: publish
permalink: /article/winnt-sendto-removable-drives.html
author: Snakefoot
excerpt: 'Configure whether it should display removable drives like Floppy, DVD and Network drives in the Send To context menu.'
type: post
id: 647
category:
    - Desktop
tag:
    - context-menu
    - network-drive
    - removable-storage-devices
    - sendto
    - windows-explorer
post_format: []
tags:
    - 'sendto,removable-storage-devices,network-drive,context-menu,windows-explorer'
---
Windows Vista extends the Send To menu with ability to show the drive-letters of the different removable drives installed (Along with mapped network drives).

- Floppy Disk Drive (A:)
- DVD/CD-CW (D:)
 
 To disable the listing of removable drives in the sendto context-menu. Create the following DWORD registry value:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoDrivesInSendToMenu = 1 (Default no value)

 Credits [Winhelponline.com](http://www.winhelponline.com/)