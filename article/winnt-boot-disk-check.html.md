---
title: 'Control disk check at boot after incorrect shutdown'
date: '2001-08-01T02:21:53+02:00'
status: publish
permalink: /article/winnt-boot-disk-check.html
author: Snakefoot
excerpt: 'Windows NT will perform a chkdsk at boot time after an improper shutdown.'
type: post
id: 186
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - chkdsk
    - file-system
    - hard-disk-drive
post_format: []
tags:
    - 'chkdsk,hard-disk-drive'
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
>  More info [MS KB191603](http://support.microsoft.com/kb/191603 "Modifying the Autochk.exe Time-out Value [Q191603]")  
>  More info [MS KB173322](http://support.microsoft.com/kb/173322 "How to Disable Autochk During a Windows NT Reboot [Q173322]")

 Note if using an USB keyboard without legacy support then one might not be able skip the the disk checking, More Info [MS KB240658](http://support.microsoft.com/kb/240658 "Cannot Skip Autocheck at Startup with USB Keyboard [Q240658]")  
  
 Note one can also use the command CHKNTFS.EXE to configure the time, along with excluding certain drives from boot up check, or forcing boot check of drives. (Running CHKNTFS.EXE /? you will see all parameters). The CHKNTFS.EXE will change the following MULTI\_SZ registry key (Use regedt32), which can be changed to force CHKDSK on all drives at boot:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  BootExecute = "autocheck autochk /f \*" (Default = "autocheck autochk \*")  
>   
>  More Info [MS KB235376](http://support.microsoft.com/kb/235376 "Disabling Autochk Causes Incorrect Volume Set Size [Q235376]")  
>  More Info [MS KB235376](http://support.microsoft.com/kb/235376 "Disabling Autochk Causes Incorrect Volume Set Size [Q235376]")

 Note if having trouble with constantly/continuously/nonexisting checking of drives at startup, then run this command to reset the above registry value to default:
 > CHKNTFS /D

 Note if wanting to query / set the dirty bit on a volume, then one can use the resource kit utility [fsutil](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/fsutil_dirty.mspx).  
  
 More info [MS KB160963](http://support.microsoft.com/kb/160963 "CHKNTFS.EXE: What You Can Use It For [Q160963]")  
 More info [MS KB218461](http://support.microsoft.com/kb/218461 "Description of Enhanced Chkdsk, Autochk, and Chkntfs Tools in Windows 2000 [Q218461]")  
 More info [MS KB235771](http://support.microsoft.com/kb/235771 "BUG: Rchelp.Sys Can Cause CHKDSK to Run Continuously [Q235771]")  
 More info [MS KB831426](http://support.microsoft.com/kb/831426 "Chkdsk.exe or Autochk.exe starts when you try to shut down or restart your computer [Q831426]")  