---
title: 'Configure Windows NT boot manager for dual-boot'
date: '2001-09-04T23:12:05+02:00'
permalink: /article/winnt-dual-boot.html
author: Snakefoot
excerpt: 'Dual booting several versions of Windows can be useful if running software which is locked to certain version of Windows.'
type: post
id: 464
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags:
    - boot-manager
    - dual-boot
---
By default when installing Windows NT on top of an existing Windows operating system, then Windows NT will adjust its boot manger during the install to include the previous operating system.  
  
 If wanting a dual-boot or multi-boot system, then the easy way is to install the oldest operating system first, and then install the newer version on top of the old one.  
  
 If already having a newer version of Windows installed, and want to dual boot with an older version of Windows, then there are two paths:

- Install the older version of Windows on the same hard disk partition as the current install, and then use the [recovery console](/article/winnt-recovery-console.html) command **fixboot** to restore the newer version of the Windows NT boot manager. Then use the [recovery console](/article/winnt-recovery-console.html) command **bootcfg** to configure the boot manager to include the older version of Windows.
- Install the older version of Windows on a new primary partition, and then change the active partition back to the hard disk partition containing the newer version of Windows with the [recovery console](/article/winnt-recovery-console.html) command **fixboot**. Then use the [recovery console](/article/winnt-recovery-console.html) command **bootcfg** to configure the boot manager to include the older version of Windows on the other partition.
 
 Microsoft has created several dual boot articles:
- <a href="https://www.bing.com/search?q=KB+184299+Q184299" rel="nofollow">Dual-Booting Windows NT 4.0 and Windows 2000 on NTFS Partitions (MS KB184299)</a>
- <a href="https://www.bing.com/search?q=KB+243896+Q243896" rel="nofollow">How to Dual Boot Windows 98 and Windows NT 4.0 with FAT16 or NTFS Volumes (MS KB243896)</a>
- <a href="https://www.bing.com/search?q=KB+153762+Q153762" rel="nofollow">How to Set Up Dual Boot After You Install Windows (MS KB153762)</a>
- <a href="https://www.bing.com/search?q=KB+136547+Q136547" rel="nofollow">Restoring Windows NT Dual Boot After Installing Windows 95 (MS KB136547)</a>
- <a href="https://www.bing.com/search?q=KB+157992+Q157992" rel="nofollow">How to Triple Boot to Windows NT, Windows 95/98, and MS-DOS (MS KB157992)</a>
- <a href="https://www.bing.com/search?q=KB+217210+Q217210" rel="nofollow">How to Multiple Boot Windows XP, Windows 2000, Windows NT, Windows 95, Windows 98, Windows Me, and MS-DOS (MS KB217210)</a>
- <a href="https://www.bing.com/search?q=KB+171444+Q171444" rel="nofollow">Removing Windows NT from a Windows 95/98 Dual-Boot Installation (MS KB171444)</a>
- <a href="https://www.bing.com/search?q=KB+285480+Q285480" rel="nofollow">How to Remove Windows 98 When It Is Part of a Dual Boot with Windows 2000 (MS KB285480)</a>
- <a href="https://www.bing.com/search?q=KB+306559+Q306559" rel="nofollow">How To Create a Multiple-Boot System in Windows XP (MS KB306559)</a>
 
 Credits [labmice.net](http://www.labmice.net)