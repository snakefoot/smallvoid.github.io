---
title: 'Configure Windows NT boot manager for dual-boot'
date: '2001-09-04T23:12:05+02:00'
status: publish
permalink: /article/winnt-dual-boot.html
author: Snakefoot
excerpt: 'Dual booting several versions of Windows can be useful if running software which is locked to certain version of Windows.'
type: post
id: 464
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-manager
    - dual-boot
post_format: []
tags:
    - 'dual-boot,boot-manager'
---
By default when installing Windows NT on top of an existing Windows operating system, then Windows NT will adjust its boot manger during the install to include the previous operating system.  
  
 If wanting a dual-boot or multi-boot system, then the easy way is to install the oldest operating system first, and then install the newer version on top of the old one.  
  
 If already having a newer version of Windows installed, and want to dual boot with an older version of Windows, then there are two paths:

- Install the older version of Windows on the same hard disk partition as the current install, and then use the [recovery console](/article/winnt-recovery-console.html) command **fixboot** to restore the newer version of the Windows NT boot manager. Then use the [recovery console](/article/winnt-recovery-console.html) command **bootcfg** to configure the boot manager to include the older version of Windows.
- Install the older version of Windows on a new primary partition, and then change the active partition back to the hard disk partition containing the newer version of Windows with the [recovery console](/article/winnt-recovery-console.html) command **fixboot**. Then use the [recovery console](/article/winnt-recovery-console.html) command **bootcfg** to configure the boot manager to include the older version of Windows on the other partition.
 
 Microsoft has created several dual boot articles:
- [Dual-Booting Windows NT 4.0 and Windows 2000 on NTFS Partitions (MS KB184299)](http://support.microsoft.com/kb/184299)
- [How to Dual Boot Windows 98 and Windows NT 4.0 with FAT16 or NTFS Volumes (MS KB243896)](http://support.microsoft.com/kb/243896)
- [How to Set Up Dual Boot After You Install Windows (MS KB153762)](http://support.microsoft.com/kb/153762)
- [Restoring Windows NT Dual Boot After Installing Windows 95 (MS KB136547)](http://support.microsoft.com/kb/136547)
- [How to Triple Boot to Windows NT, Windows 95/98, and MS-DOS (MS KB157992)](http://support.microsoft.com/kb/157992)
- [How to Multiple Boot Windows XP, Windows 2000, Windows NT, Windows 95, Windows 98, Windows Me, and MS-DOS (MS KB217210)](http://support.microsoft.com/kb/217210)
- [Removing Windows NT from a Windows 95/98 Dual-Boot Installation (MS KB171444)](http://support.microsoft.com/kb/171444)
- [How to Remove Windows 98 When It Is Part of a Dual Boot with Windows 2000 (MS KB285480)](http://support.microsoft.com/kb/285480)
- [How To Create a Multiple-Boot System in Windows XP (MS KB306559)](http://support.microsoft.com/kb/306559)
 
 Credits [labmice.net](http://www.labmice.net)