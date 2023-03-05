---
title: 'Restore boot manager when NTLDR is missing'
date: '2006-02-25T01:59:43+01:00'
status: publish
permalink: /article/winnt-restore-ntldr.html
author: Snakefoot
excerpt: 'Windows NT will fail to boot if it cannot find the files used to load the boot manager.'
type: post
id: 475
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-manager
    - ntldr
    - system-recovery
post_format: []
tags:
    - 'boot-manager,ntldr,system-recovery'
---
The [NT Loader](/article/winnt-update-boot-manager.html) (NTLDR) is part of the Windows NT boot files. If the NTLDR becomes corrupted, then Windows NT will fail to boot and give messages like:

> *NTLDR is missing  
>   
>  Boot: Couldn't find NTLDR. Please insert another disk.*

 Usually this problem can be solved by [checking the boot devices](/article/no-boot-device-found.html). If no problems found then one can try to restore the boot manager files in case they have become damaged:
- Ntldr
- Ntdetect.com
- [Boot.ini](/article/winnt-boot-ini.html)
 
 If using Windows 2000/XP then one can restore the boot files using the [Recovery Console](/article/winnt-recovery-console.html), and copy the NtLdr and Ntdetect.com (NOT Boot.ini) from the Windows 2000/XP install CD to the boot partition. And if using Windows XP then one can try to rebuild the boot.ini file using the recovery console command "bootcfg /rebuild". More Info [MS KB318728](http://support.microsoft.com/kb/318728 "How to troubleshoot the "NTLDR Is Missing" error message in Windows 2000 [Q318728]")  
  
 If using Windows NT4/2000/XP then one can create a custom bootable floppy containing the boot files. Where the Boot.ini points to the boot partition, so when booting from the floppy it will load Windows NT from the boot partition and allow one to repair the boot files within Windows NT. More Info [MS KB119467](http://support.microsoft.com/kb/119467 "How to Create a Bootable Disk for an NTFS or FAT Partition [Q119467]")  
  
 Note the chance of damaged boot files is higher if the boot partition is using FAT16/FAT32, where the filesystem is easily damaged [compared to NTFS](/article/cluster-hard-disk-partition.html). If using NTFS, then it can be a sign that the hard disk is starting to fail, and one should take a backup of important files and acquire a disk diagnostic utility from the hard disk manufacture.  
  
 More Info [MS KB100312](http://support.microsoft.com/kb/100312 "Error messages during boot Sequence on Intel x86 machines [Q100312]")  
 More Info [MS KB124550](http://support.microsoft.com/kb/124550 ""Windows NT Could Not Start...Ntoskrnl.exe" error message [Q124550]")  
 More Info [MS KB320397](http://support.microsoft.com/kb/320397 "You receive an "NTLDR is missing" error message when you start your computer [Q320397]")  
  
 Note if the NT Loader (Ntldr) have become compressed, then it will fail because all features of NTFS is not available during booting and give the error "NTLDR is compressed". To decompress the Ntldr use the [Recovery Console](/article/winnt-recovery-console.html) and execute these two commands:
1. > CD \\
2. > ATTRIB -C NTLDR
 
 Credits [ComputerHope.com](http://www.computerhope.com/issues/ch000465.htm)