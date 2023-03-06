---
title: 'Configure performance counters in Windows NT'
date: '2001-02-05T23:49:10+01:00'
status: publish
permalink: /article/winnt-performance-counters.html
author: Snakefoot
excerpt: 'How to activate performance counters for the different performance objects in Windows NT.'
type: post
id: 373
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - performance-counters
post_format: []
tags:
    - performance-counters
---
Performance counters are enabled by default to allow applications such as [Performance Logs and Alerts](/article/winnt-services-sysmonlog.html) to subscribe to these counters and measure performance. One can disable these performance counters to free resources.  
  
 There is a tool in the Win2k resource kit called [Exctrlst.exe](http://www.microsoft.com/windows2000/techinfo/reskit/tools/existing/exctrlst-o.asp), which makes it easy to disable performance counters for installed services:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\**Service Name** \\Performance\]  
>  Disable Performance Counters = 1  
>   
>  More Info [MS KB179456](http://support.microsoft.com/kb/179456 "Extensible Counters in Performance Monitor [Q179456]")  
>  More Info [MS KB248993](http://support.microsoft.com/kb/248993 "PRB: Performance Object Is Not Displayed in Performance Monitor [Q248993]")  
>  More Info [MS KB266416](http://support.microsoft.com/kb/266416 "How to Troubleshoot WinMgmt-Based Performance Counter Errors [Q266416]")

 There is a PhysicalDisk object, which allows monitoring of physical disks and logical drives. Windows 2000 monitors the physical disks by default, and it can be turned off by running this command and perform a reboot:
>  DISKPERF -N  
>   
>  To turn it on again run this command:  
>   
>  DISKPERF -YD  
>   
>  Note Windows XP only activates monitoring of the physical disks and logical drives on demand.  
>   
>  More Info [MS KB253251](http://support.microsoft.com/kb/253251 "Using Diskperf in Windows 2000 [Q253251]")  
>  More Info [MS KB296187](http://support.microsoft.com/kb/296187 "Application Log Events Generated When You Start Performance Counter Query [Q296187]")

 There is an I/O counter, which monitors the I/O for each process (Can be seen in the Task Manager with the columns I/O Writes, I/O Other, etc.). If this monitoring information is not important then one can disable it with this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\I/O System\]  
>  CountOperations = 0 (Default = Key does not exist)

 Credits [ntcompatible.com](http://www.ntcompatible.com/)  