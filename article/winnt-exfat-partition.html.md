---
title: 'Access exFAT partitions from Windows XP'
date: '2008-12-23T05:09:08+01:00'
status: publish
permalink: /article/winnt-exfat-partition.html
author: Snakefoot
excerpt: 'How to install the Vista exFAT file system driver on Windows XP.'
type: post
id: 784
category:
    - Troubleshoot
tag:
    - exFAT
    - file-system
post_format: []
tags:
    - 'exfat,file-system'
---
Microsoft have created the exFAT filesystem to better support flash drives. It is a proprietary file system that was introduced with Vista SP1. More Info [Filesystem Comparison](/article/cluster-hard-disk-partition.html)  
  
 The exFAT/FAT64 filesystem is only supported for Windows Vista/2008/CE 6.0, and it is not possible by default to access exFAT partitions from other versions of Windows.  
  
 Microsoft have now released an [official driver update for Windows XP](http://www.microsoft.com/downloads/details.aspx?FamilyID=1cbe3906-ddd1-4ca2-b727-c2dff5e30f61), that allows one to access exFAT partitions. More Info [MS KB955704](http://support.microsoft.com/kb/955704 "Description of the exFAT file system driver update package")

##### Unofficial way of installing exFAT support

 Before Microsoft released the official update for Windows XP, then one had to apply a few hacks to make it possible to use the Vista exFAT file system driver on Windows XP (and maybe other versions of Windows):
1. Download the [exFAT File System Driver](http://smallvoid.orgfree.com/?file=exfat_file_system_driver.zip)
2. Copy **exfat.sys** and **uexfat.dll** into these directories: 
  - %windir%\\System32\\Drivers
  - %windir%\\System32
3. Copy the Reg code, given below into Notepad and Save as **exFAT.reg**:
  > Windows Registry Editor Version 5.00  
  >   
  >  \[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\exfat\]  
  >  "Description"="exFAT File System Driver"  
  >  "DisplayName"="exFAT File System Driver"  
  >  "ErrorControl"=dword:00000001  
  >  "Group"="Boot File System"  
  >  "Start"=dword:00000002  
  >  "Type"=dword:00000002  
  >   
  >  \[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\System\\exfat\]  
  >  "EventMessageFile"=hex(2):25,00,53,00,79,00,73,00,74,00,65,00,6d,00,52,00,6f,\\  
  >  00,6f,00,74,00,25,00,5c,00,53,00,79,00,73,00,74,00,65,00,6d,00,33,00,32,00,\\  
  >  5c,00,49,00,6f,00,4c,00,6f,00,67,00,4d,00,73,00,67,00,2e,00,64,00,6c,00,6c,\\  
  >  00,00,00  
  >  "TypesSupported"=dword:00000007
4. Double click the newly created reg-file **exFAT.reg** to activate the driver
5. Restart the computer
 
 Note make sure to create a system restore point before starting this procedure. It should be possible to use [Last Known Good Configuration](/article/winnt-last-known-good-configuration.html) to restore the system if the operation goes bad.  
  
 Credits [ItsMyWindows.com](http://www.itsmywindows.com/how-to-access-exfat-formatted-partition-or-removable-devices-in-windows-xp)