---
title: 'Control disk check at boot after incorrect shutdown'
date: '2001-08-01T02:21:53+02:00'
permalink: /article/winnt-boot-disk-check.html
author: Snakefoot
excerpt: 'Windows NT will perform a chkdsk at boot time after an improper shutdown.'
type: post
id: 186
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
    - windows-vista_troubleshoot
tags:
    - chkdsk
    - file-system
    - hard-disk-drive
---
After an incorrect/improper shutdown, then Windows will perform a CHKDSK of the partitions marked with a dirty-bit at boot to ensure disk stability.  
 One can also force CHKDSK to run at next boot if running CHKDSK /F on a partition that is "locked". The partition becomes locked if applications have files open on the partition (Ex. using Windows Explorer to open a folder on the partition):

> Chkdsk cannot run because the volume is in use by another process. Would you like to schedule this volume to be checked the next time the system restarts? (Y/N)

 When booting the CHKDSK is not started before a timer has expired, allowing the user to avoid running CHKDSK at boot.
 > *To skip disk checking, press any key within 10 seconds.*

 The timer is in seconds and can be controlled with this DWORD :  
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  AutoChkTimeOut=10 (Default = 10, Disable Countdown=0)  
>   
>  More info <a href="https://www.bing.com/search?q=KB+191603+Q191603" rel="nofollow" title="Modifying the Autochk.exe Time-out Value [Q191603]">MS KB191603</a>  
>  More info <a href="https://www.bing.com/search?q=KB+173322+Q173322" rel="nofollow" title="How to Disable Autochk During a Windows NT Reboot [Q173322]">MS KB173322</a>

 Note if using an USB keyboard without legacy support then one might not be able skip the the disk checking, More Info <a href="https://www.bing.com/search?q=KB+240658+Q240658" rel="nofollow" title="Cannot Skip Autocheck at Startup with USB Keyboard [Q240658]">MS KB240658</a>  
  
 Note one can also use the command CHKNTFS.EXE to configure the time, along with excluding certain drives from boot up check, or forcing boot check of drives. (Running CHKNTFS.EXE /? you will see all parameters). The CHKNTFS.EXE will change the following MULTI\_SZ registry key (Use regedt32), which can be changed to force CHKDSK on all drives at boot:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  BootExecute = "autocheck autochk /f \*" (Default = "autocheck autochk \*")  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+235376+Q235376" rel="nofollow" title="Disabling Autochk Causes Incorrect Volume Set Size [Q235376]">MS KB235376</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+235376+Q235376" rel="nofollow" title="Disabling Autochk Causes Incorrect Volume Set Size [Q235376]">MS KB235376</a>

 Note if having trouble with constantly/continuously/nonexisting checking of drives at startup, then run this command to reset the above registry value to default:
 > CHKNTFS /D

 Note if wanting to query / set the dirty bit on a volume, then one can use the resource kit utility [fsutil](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/fsutil_dirty.mspx).  
  
 More info <a href="https://www.bing.com/search?q=KB+160963+Q160963" rel="nofollow" title="CHKNTFS.EXE: What You Can Use It For [Q160963]">MS KB160963</a>  
 More info <a href="https://www.bing.com/search?q=KB+218461+Q218461" rel="nofollow" title="Description of Enhanced Chkdsk, Autochk, and Chkntfs Tools in Windows 2000 [Q218461]">MS KB218461</a>  
 More info <a href="https://www.bing.com/search?q=KB+235771+Q235771" rel="nofollow" title="BUG: Rchelp.Sys Can Cause CHKDSK to Run Continuously [Q235771]">MS KB235771</a>  
 More info <a href="https://www.bing.com/search?q=KB+831426+Q831426" rel="nofollow" title="Chkdsk.exe or Autochk.exe starts when you try to shut down or restart your computer [Q831426]">MS KB831426</a>  