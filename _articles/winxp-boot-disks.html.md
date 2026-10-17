---
title: 'Windows XP setup boot floppy disks'
date: '2001-11-01T15:24:07+01:00'
permalink: /article/winxp-boot-disks.html
author: Snakefoot
excerpt: 'Using floppy disks to perform the install of Windows XP.'
type: post
id: 497
categories:
    - windows-xp_utilities
tags:
    - bootdisk
    - cdrom-drive
    - floppy-disk
    - windows-install
---
Microsoft have released <a href="https://www.bing.com/search?q=KB+310994+Q310994" title="How to obtain Windows XP Setup disks for a floppy boot installation [Q310994]" rel="nofollow">xp boot disks</a> that makes it possible to launch the Windows XP setup using the floppy drive (Includes the recovery console). This can be useful in the situation where one cannot boot from the cdrom drive, but it requires that one creates 6 floppy disks.  
  
 Note one can also install Windows XP using a single [DOS bootdisk](/article/dos-bootdisk.html). Just make sure it has CD-ROM drivers along with [smartdrv](/article/hdd-disk-cache-smartdrv.html) loaded, as it will make the install faster. Start the install with this command (Where X: is the CD-ROM driveletter):

> X:\\i386\\Winnt.exe

 Note if just wanting a DOS bootdisk after having installed WinXP, just open My Computer and right click the floppy drive and select Format and check "Create an Ms-DOS startup disk".  
  
 Note one can use the WinXP bootdisks in conjunction with [ChkReg.exe](http://www.microsoft.com/downloads/details.aspx?FamilyID=56d3c201-2c68-4de8-9229-ca494362419c), which is a Windows 2000 Registry Repair Utility (Though one should make a backup of the registry files before trying to repair them).  
  
 More Info <a href="https://www.bing.com/search?q=KB+316941+Q316941" rel="nofollow" title="HOW TO: Install Windows XP [Q316941]">MS KB316941</a>  