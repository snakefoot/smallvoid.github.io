---
title: 'Configure cleanup profiles to remove unnecessary files'
date: '2002-10-28T23:31:50+01:00'
status: publish
permalink: /article/cleanup-profiles.html
author: Snakefoot
excerpt: 'How to create different profiles for cleaning up the hard disk.'
type: post
id: 124
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - cleanup-tool
    - compress
    - free-disk-space
    - scheduled-task
    - temporary-files
post_format: []
tags:
    - 'cleanup-tool,compress,temporary-files,scheduled-task,free-disk-space'
---
The Clean Up tool was introduced with Win98 to automate the procedure of cleaning up unnecessary temporary files. It is mainly for people who is having a hard time figuring out what they have on their drives. It has been updated in WinMe/2k/XP, where it is possible to setup different Clean Up profiles.  
  
 To configure a profile run the following command (Where N is a profile number from 0-65535):

> cleanmgr /sageset:N

 To run a configured profile number (N) run the following command:
 
> cleanmgr /sagerun:N

 This can be used to create a shortcut to clean up Temporary Internet Files, or schedule a weekly cleanup of the Recycle Bin using the Task Scheduler, or if using Windows 2000, XP schedule to Compress old files.  
  
 Note Win98/WinMe can also use profiles for configuring [defrag](/article/win9x-defrag-switches.html) and [scandisk](/article/win9x-scandisk-switches.html) for scheduling.  
  
 Note Win2k/WinXP includes a new feature that **Compress old files** not used the last ? days, by using [NTFS compression](/article/winnt-ntfs-compress.html) (blue files). Even if having this option disabled it might still do "Scanning: Compress old files", which can be slow and make it hang for a long time (It is also activated when doing a defrag). To disable it by force, delete the following registry keys (Make an export first):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Explorer \\VolumeCaches \\**Compress old files**\]  
>   
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Classes \\CLSID \\**{B50F5260-0C21-11D2-AB56-00A0C9082678}**\]  
>   
>  More Info [MS KB812248](http://support.microsoft.com/kb/812248 "Disk Cleanup Tool Stops Responding While Compressing Old Files [Q812248]")  
>  More Info [MS KB886219](http://support.microsoft.com/kb/886219 "The Disk Cleanup tool in Windows 2000 stops responding while it scans old files for compression [Q886219]")

 More Info [MS KB186099](http://support.microsoft.com/kb/186099 "Description of the Disk Cleanup Tool [Q186099]")  
 More Info [MS KB253597](http://support.microsoft.com/kb/253597 "Automating Disk Cleanup Tool in Windows [Q253597]")  
 More Info [MS KB269020](http://support.microsoft.com/kb/269020 "Cleanmgr.exe Adds Incorrect Error Entry to Schedlog.txt File [Q269020]")  
 More Info [MS KB310312](http://support.microsoft.com/kb/310312 "Description of the Disk Cleanup Tool in Windows XP [Q310312]")  
  
 Credits [nightcourses.com](http://nightcourses.com/)