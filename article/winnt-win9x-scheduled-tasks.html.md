---
title: 'Disable checking for scheduled tasks when browsing Win9x shares'
date: '2001-01-01T00:01:43+01:00'
status: publish
permalink: /article/winnt-win9x-scheduled-tasks.html
author: Snakefoot
excerpt: 'When accessing the shares of a Win9x machine, then time is spend on checking for scheduled tasks.'
type: post
id: 441
category:
    - Network
tag:
    - network-performance
    - network-share
    - scheduled-task
post_format: []
tags:
    - 'scheduled-task,network-share,network-performance'
---
Accessing Win9x/Me shares can be slow, this can be caused by remotely checking for scheduled tasks and printers on the Win9x/Me machine.  
  
 To disable this checking go to this registry key:

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\RemoteComputer \\NameSpace\]

 There you will find these sub-keys:  
> {D6277990-4C6A-11CF-8D87-00AA0060F5BF} (Scheduled Tasks)  
>  {2227A280-3AEA-1069-A2DE-08002B30309D} (Printers)

 By deleting these sub-keys the checking will be disabled.  
  
 Note a backup should be made of the registry keys before deleting them in case one need to restore it.  
  
 More Info [MS KB245800](http://support.microsoft.com/kb/245800 "Delay Viewing Shares on a Microsoft Windows 98-Based Computer From a Windows 2000-Based Computer [Q245800]")  
  
 Credits [jsifaq.com](http://www.jsifaq.com/)