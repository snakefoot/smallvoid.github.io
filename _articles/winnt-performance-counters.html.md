---
title: 'Configure performance counters in Windows NT'
date: '2001-02-05T23:49:10+01:00'
permalink: /article/winnt-performance-counters.html
author: Snakefoot
excerpt: 'How to activate performance counters for the different performance objects in Windows NT.'
type: post
id: 373
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-xp_performance
tags:
    - performance-counters
---
Performance counters are enabled by default to allow applications such as [Performance Logs and Alerts](/article/winnt-services-sysmonlog.html) to subscribe to these counters and measure performance. One can disable these performance counters to free resources.  
  
 There is a tool in the Win2k resource kit called [Exctrlst.exe](http://www.microsoft.com/windows2000/techinfo/reskit/tools/existing/exctrlst-o.asp), which makes it easy to disable performance counters for installed services:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\**Service Name** \\Performance\]  
>  Disable Performance Counters = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20179456%20Q179456" rel="nofollow" title="Extensible Counters in Performance Monitor [Q179456]">MS KB179456</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20248993%20Q248993" rel="nofollow" title="PRB: Performance Object Is Not Displayed in Performance Monitor [Q248993]">MS KB248993</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20266416%20Q266416" rel="nofollow" title="How to Troubleshoot WinMgmt-Based Performance Counter Errors [Q266416]">MS KB266416</a>

 There is a PhysicalDisk object, which allows monitoring of physical disks and logical drives. Windows 2000 monitors the physical disks by default, and it can be turned off by running this command and perform a reboot:
>  DISKPERF -N  
>   
>  To turn it on again run this command:  
>   
>  DISKPERF -YD  
>   
>  Note Windows XP only activates monitoring of the physical disks and logical drives on demand.  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20253251%20Q253251" rel="nofollow" title="Using Diskperf in Windows 2000 [Q253251]">MS KB253251</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20296187%20Q296187" rel="nofollow" title="Application Log Events Generated When You Start Performance Counter Query [Q296187]">MS KB296187</a>

 There is an I/O counter, which monitors the I/O for each process (Can be seen in the Task Manager with the columns I/O Writes, I/O Other, etc.). If this monitoring information is not important then one can disable it with this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\I/O System\]  
>  CountOperations = 0 (Default = Key does not exist)

 Credits [ntcompatible.com](http://www.ntcompatible.com/)  