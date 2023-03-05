---
title: 'Windows XP setup boot floppy disks'
date: '2001-11-01T15:24:07+01:00'
status: publish
permalink: /article/winxp-boot-disks.html
author: Snakefoot
excerpt: 'Using floppy disks to perform the install of Windows XP.'
type: post
id: 497
category:
    - Utilities
tag:
    - bootdisk
    - cdrom-drive
    - floppy-disk
post_format: []
tags:
    - 'bootdisk,floppy-disk,cdrom-drive'
---
Microsoft have released [xp boot disks](http://support.microsoft.com/kb/310994 "How to obtain Windows XP Setup disks for a floppy boot installation [Q310994]") that makes it possible to launch the Windows XP setup using the floppy drive (Includes the recovery console). This can be useful in the situation where one cannot boot from the cdrom drive, but it requires that one creates 6 floppy disks.  
  
 Note one can also install Windows XP using a single [DOS bootdisk](/article/dos-bootdisk.html). Just make sure it has CD-ROM drivers along with [smartdrv](/article/hdd-disk-cache-smartdrv.html) loaded, as it will make the install faster. Start the install with this command (Where X: is the CD-ROM driveletter):

> X:\\i386\\Winnt.exe

 Note if just wanting a DOS bootdisk after having installed WinXP, just open My Computer and right click the floppy drive and select Format and check "Create an Ms-DOS startup disk".  
  
 Note one can use the WinXP bootdisks in conjunction with [ChkReg.exe](http://www.microsoft.com/downloads/details.aspx?FamilyID=56d3c201-2c68-4de8-9229-ca494362419c), which is a Windows 2000 Registry Repair Utility (Though one should make a backup of the registry files before trying to repair them).  
  
 More Info [MS KB316941](http://support.microsoft.com/kb/316941 "HOW TO: Install Windows XP [Q316941]")  