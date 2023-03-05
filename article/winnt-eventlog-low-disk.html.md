---
title: 'Configure when to report low on disk space in the Event Log'
date: '2001-01-01T19:10:27+01:00'
status: publish
permalink: /article/winnt-eventlog-low-disk.html
author: Snakefoot
excerpt: 'Change the treshold of when to report that a disk is near its capacity.'
type: post
id: 382
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - event-log
    - hard-disk-drive
post_format: []
tags:
    - 'event-log,hard-disk-drive'
---
The System Event Log will display the following warning when less than 10% disk space is free:

> Event ID - 2013  
>   
>  The &lt;disk-letter&gt; disk is at or near capacity. You might need to delete some files.

 To configure the percentage of free space the disk should have left before writing an entry to EventLog edit this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  DiskSpaceThreshold=0 (0-99 percent, Default = 10%)  
>   
>  More Info [MS KB112509](http://support.microsoft.com/kb/112509 "Error 2013 - Disk Is At Or Near Capacity [Q112509]")

 Windows 2003 can also write an entry to the Eventlog when the free space on disk is below a certain treshold specified in megabytes:
 
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  LowDiskSpaceMinimum=0 (Default = 400 MByte)

Related [Show warning in taskbar when low on HDD space in WinXP](/article/winnt-taskbar-low-disk.html)