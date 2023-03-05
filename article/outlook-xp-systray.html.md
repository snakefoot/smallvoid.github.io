---
title: 'Minimize Outlook XP to systray instead of using taskbar'
date: '2002-03-30T18:40:17+01:00'
status: publish
permalink: /article/outlook-xp-systray.html
author: Snakefoot
excerpt: 'Outlook can be minimized to the system tray so it will not be filling up on the taskbar.'
type: post
id: 333
category:
    - Outlook
tag:
    - system-tray
post_format: []
tags:
    - system-tray
---
By default when running Outlook XP(2002) it clutters the taskbar, one can make it into an icon on the system tray. This is done with this DWORD in registry :

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Office \\10.0 \\Outlook \\Preferences\]  
>  MinToTray = 1 (Default = 0, Enabled = 1, Disabled = 0)

 Note in Outlook 2003 it can be done by Right-clicking the Outlook icon in the notification area, and select "Hide When Minimized" in the shortcut menu. More Info [MS KB833007](http://support.microsoft.com/kb/833007 "How to change the behavior of the Cancel Request dialog box in Outlook 2003 [Q833007]")  
  
 Note when having enabled minimize to tray, then it is possible to make Outlook automatically place it self in the systray when it is started. This is done by creating a shortcut to the Outlook icon, which starts Outlook in minimized state. More Info [MS KB251340](http://support.microsoft.com/kb/251340 "How to start Outlook 2002 or Outlook 2000 in a minimized state [Q251340]").