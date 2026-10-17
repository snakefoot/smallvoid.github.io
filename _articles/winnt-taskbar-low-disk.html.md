---
title: 'Disable running low on disk space notification in the taskbar'
date: '2001-10-07T19:51:13+02:00'
permalink: /article/winnt-taskbar-low-disk.html
author: Snakefoot
excerpt: 'Display a warning when the when a hard disk is near its capacity'
type: post
id: 383
categories:
    - windows-xp_tips
tags:
    - desktop
    - windows-explorer
    - hard-disk-drive
    - taskbar
---
You can control whether it should display warnings about low on hard disk space, with the following DWORD registry setting:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoLowDiskSpaceChecks = 1 (Show = 0, Don't Show = 1, Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20285107%20Q285107" rel="nofollow" title="Description of the Low Disk Space Notification in Windows XP [Q285107]">MS KB285107</a>

 Related [Changing when to report low on HDD space in Event Log](/article/winnt-eventlog-low-disk.html)  
  
 Credits [ntfaq.com](http://www.ntfaq.com/)