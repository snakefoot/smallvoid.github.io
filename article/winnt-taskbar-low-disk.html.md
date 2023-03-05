---
title: 'Disable running low on disk space notification in the taskbar'
date: '2001-10-07T19:51:13+02:00'
status: publish
permalink: /article/winnt-taskbar-low-disk.html
author: Snakefoot
excerpt: 'Display a warning when the when a hard disk is near its capacity'
type: post
id: 383
category:
    - Desktop
tag:
    - hard-disk-drive
    - taskbar
post_format: []
tags:
    - 'taskbar,hard-disk-drive'
---
You can control whether it should display warnings about low on hard disk space, with the following DWORD registry setting:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoLowDiskSpaceChecks = 1 (Show = 0, Don't Show = 1, Default = 0)  
>   
>  More Info [MS KB285107](http://support.microsoft.com/kb/285107 "Description of the Low Disk Space Notification in Windows XP [Q285107]")

 Related [Changing when to report low on HDD space in Event Log](/article/winnt-eventlog-low-disk.html)  
  
 Credits [ntfaq.com](http://www.ntfaq.com/)