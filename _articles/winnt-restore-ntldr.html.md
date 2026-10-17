---
title: 'Restore boot manager when NTLDR is missing'
date: '2006-02-25T01:59:43+01:00'
permalink: /article/winnt-restore-ntldr.html
author: Snakefoot
excerpt: 'Windows NT will fail to boot if it cannot find the files used to load the boot manager.'
type: post
id: 475
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags:
    - boot-manager
    - ntldr
    - system-recovery
---
The [NT Loader](/article/winnt-update-boot-manager.html) (NTLDR) is part of the Windows NT boot files. If the NTLDR becomes corrupted, then Windows NT will fail to boot and give messages like:

> *NTLDR is missing  
>   
>  Boot: Couldn't find NTLDR. Please insert another disk.*

 Usually this problem can be solved by [checking the boot devices](/article/no-boot-device-found.html). If no problems found then one can try to restore the boot manager files in case they have become damaged:
- Ntldr
- Ntdetect.com
- [Boot.ini](/article/winnt-boot-ini.html)
 
 If using Windows 2000/XP then one can restore the boot files using the [Recovery Console](/article/winnt-recovery-console.html), and copy the NtLdr and Ntdetect.com (NOT Boot.ini) from the Windows 2000/XP install CD to the boot partition. And if using Windows XP then one can try to rebuild the boot.ini file using the recovery console command "bootcfg /rebuild". More Info <a href="https://www.bing.com/search?q=KB%20318728%20Q318728" rel="nofollow" title="How to troubleshoot the 'NTLDR Is Missing' error message in Windows 2000 [Q318728]">MS KB318728</a>  
  
 If using Windows NT4/2000/XP then one can create a custom bootable floppy containing the boot files. Where the Boot.ini points to the boot partition, so when booting from the floppy it will load Windows NT from the boot partition and allow one to repair the boot files within Windows NT. More Info <a href="https://www.bing.com/search?q=KB%20119467%20Q119467" rel="nofollow" title="How to Create a Bootable Disk for an NTFS or FAT Partition [Q119467]">MS KB119467</a>  
  
 Note the chance of damaged boot files is higher if the boot partition is using FAT16/FAT32, where the filesystem is easily damaged [compared to NTFS](/article/cluster-hard-disk-partition.html). If using NTFS, then it can be a sign that the hard disk is starting to fail, and one should take a backup of important files and acquire a disk diagnostic utility from the hard disk manufacture.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20100312%20Q100312" rel="nofollow" title="Error messages during boot Sequence on Intel x86 machines [Q100312]">MS KB100312</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20124550%20Q124550" rel="nofollow" title="'Windows NT Could Not Start...Ntoskrnl.exe' error message [Q124550]">MS KB124550</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20320397%20Q320397" rel="nofollow" title="You receive an 'NTLDR is missing' error message when you start your computer [Q320397]">MS KB320397</a>  
  
 Note if the NT Loader (Ntldr) have become compressed, then it will fail because all features of NTFS is not available during booting and give the error "NTLDR is compressed". To decompress the Ntldr use the [Recovery Console](/article/winnt-recovery-console.html) and execute these two commands:
 > CD \\
 > ATTRIB -C NTLDR
 
 Credits [ComputerHope.com](http://www.computerhope.com/issues/ch000465.htm)