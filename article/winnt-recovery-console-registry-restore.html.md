---
title: 'Using Recovery Console to restore registry files'
date: '2004-06-10T01:02:38+02:00'
status: publish
permalink: /article/winnt-recovery-console-registry-restore.html
author: Snakefoot
excerpt: 'The Recovery Console allows one to restore the registry as part of system recovery.'
type: post
id: 252
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - recovery-console
    - system-recovery
post_format: []
tags:
    - 'system-recovery,recovery-console'
---
The [Recovery Console](/article/winnt-recovery-console.html) allows one to copy and move files. It can be useful in the situation where the registry files have become faulty, making it impossible to boot Windows normally.  
  
 The active machine registry files are placed here:

> %systemroot%\\System32\\Config\\system  
>  %systemroot%\\System32\\Config\\software  
>  %systemroot%\\System32\\Config\\sam  
>  %systemroot%\\System32\\Config\\security  
>  %systemroot%\\System32\\Config\\default

 The active user registry file is placed here:
 > %SystemRoot%\\Profiles\\&lt;Username&gt;\\Ntuser.dat (WinNT4)  
 > C:\\Documents and Settings\\&lt;Username&gt;\\Ntuser.dat (Win2k/WinXP)

 The initial registry files are placed here (Created at install):
 > %systemroot%\\System32\\Repair\\system  
 > %systemroot%\\System32\\Repair\\software

 If having used [Ntbackup](/article/winnt-ntbackup.html) to create a System State backup, then a copy of the registry files will be placed in the following directory:
 - Win2k (Also happens when creating a Emergency Recovery Disk):
   > %systemroot%\\System32\\Repair\\RegBack  
   >   
   >  More Info [MS KB231777](http://support.microsoft.com/kb/231777 "How to Create an Emergency Repair Disk in Windows 2000 [Q231777]")
 - WinXP:
   > %systemroot%\\Repair
 
 If using WinNT4/Win2k then one can find a recent backup of the System-registry here:
 > %systemroot%\\System32\\Config\\System.alt  
>   
>  More Info [MS KB151247](http://support.microsoft.com/kb/151247 "Using System.alt to Recover the System Hive [Q151247]")

 Related [Offline registry editing](/article/winnt-offline-registry-edit.html)  
  
 More Info [MS KB269075](http://support.microsoft.com/kb/269075 "Error Message: Windows Could Not Start Because the Following File Is Missing or Corrupt: \Winnt\System32\Config\Systemced [Q269075]")  
 More Info [MS KB307545](http://support.microsoft.com/kb/307545 "How to Recover from a Corrupted Registry that Prevents Windows XP from Starting [Q307545]")  