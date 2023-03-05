---
title: 'Configure monitoring of application startup'
date: '2003-05-25T23:58:57+02:00'
status: publish
permalink: /article/win9x-application-log.html
author: Snakefoot
excerpt: 'Save resources by disabling the Task Monitor and avoid the logging of every application startup.'
type: post
id: 102
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - defrag
    - task-monitor
post_format: []
tags:
    - 'task-monitor,defrag'
---
Windows 98 introduced a new feature for optimizing the startup of applications called the Task Monitor. The Task Monitor monitors the file operations of all applications during their startup phase. The Disk Defragmenter then uses the logs created from monitoring the applications, to group the files (DLL's etc.) used by the application together, so the file operations will be faster next time the application starts.  
  
 The Task Monitor (Taskmon.exe) creates the \*.Lgc files in C:\\Windows\\Applog. The Taskmon.exe cannot be seen when doing CTRL+ALT+DEL, but it can disabled using Msconfig, where it is listed in the Startup-Tab (If not it is already disabled). If having a low end computer then one should consider disabling the Task Monitor as it uses resources for monitoring applications and leads to even lower performance.  
  
 The Defrag creates the file C:\\Windows\\Applog\\Optlog.txt, which contains the information of what optimizations have been done. One can disable defrag from using the Applog entries by starting Defrag and click the Settings-Button and untick "Rearrange program files so my programs starts faster" (Not recommended).  
  
 The defrag can be configured even more:

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Applets \\Defrag \\AppStartParams\]  
>  UseProfile = 1 (Enables the use of the \*.Lgc files in Applog)  
>  MinLogSize = 1000 (Ignores all \*.Lgc files below 1000 bytes)  
>  MaxNoUseDays = 90 (Ignores all \*.Lgc files older than 90 days, 0 = Ignore age)  
>  MaxApps = 50 (Only optimizes the 50 most used applications)  
>  ExcludeFiles = "System.dat\\User.dat\\System.ini\\Win.ini" (What files NOT to optimize)

 Note some recommend that only activating the TaskMonitor when a new application is installed, where one starts and stops the new application a few times, then disable the Task Monitor again. This will generate a lgc file for the new application so defrag will keep it optimized.  
  
 More Info [MS Technet](http://www.microsoft.com/technet/prodtechnol/win98/reskit/part2/wrkc10.asp "Microsoft Windows 98 Resource Kit - Chapter 10 - Disks and File Systems")  
 More Info [MS KB186020](http://support.microsoft.com/kb/186020 "How to Determine the Programs Disk Defragmenter Optimizes [Q186020]")  
 More Info [MS KB186171](http://support.microsoft.com/kb/186171 "Description of the Disk Defragmenter Tool in Windows 98/Me [Q186171]")  
 More Info [MS KB197791](http://support.microsoft.com/kb/197791 "Error Message: TASKMON Caused an Invalid Page Fault in Module... [Q197791]")  
  
 Related [Defrag partitions to speed up file access](/article/defrag-hard-disk-partition.html)  
 Related [Faster defrag in Windows 98 using defrag from WinMe](/article/winme-defrag.html)  