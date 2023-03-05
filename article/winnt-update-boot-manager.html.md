---
title: 'Updating the Windows NT boot manager'
date: '2002-01-01T02:03:27+01:00'
status: publish
permalink: /article/winnt-update-boot-manager.html
author: Snakefoot
excerpt: 'Windows XP boot manager is faster and can be used on Windows 2000.'
type: post
id: 474
category:
    - Utilities
    - Utilities
tag:
    - boot-manager
post_format: []
tags:
    - boot-manager
---
Windows XP has its bootup sequence optimized compared to Windows 2000. One can take the files for the Windows XP boot manager and apply them to Windows 2000.  
  
 The [WinXP Boot Manager](http://smallvoid.orgfree.com/?file=xp_boot.zip) consists of two files that one should copy to the root of the Windows 2000 boot-partition:

- NTLDR (NT Loader) 
  - Switches to 32-bit memory
  - Starts mini-file system
  - Reads [BOOT.INI](/article/winnt-boot-ini.html) and present selection
  - Starts NTDETECT
  - Starts NTOSKRNL
  - Loads [Hardware Abstraction Layer](/article/winnt-hardware-abstraction-layer.html) (HAL), registry hives and drivers
- NTDETECT 
  - Scans hardware
  - Returns hardware list back to NTLDR
 
 More Info [MS KB100323](http://support.microsoft.com/kb/100323 "Intel x86-Based System Boot Sequence and Files [Q100323]")  