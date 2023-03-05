---
title: 'Manage temporary files to minimize file fragmentation'
date: '2000-01-01T03:02:02+01:00'
status: publish
permalink: /article/windows-temporary-files.html
author: Snakefoot
excerpt: 'How temporary files cause file fragmentation and different RAM disk options.'
type: post
id: 235
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - defrag
    - ram-disk
post_format: []
tags:
    - 'ram-disk,defrag'
---
Directories containing temporary files usually see a lot of file operations, and besides causing an overhead for the HDD performing the operations, then it also increases the chance of [file fragmentation](/article/defrag-hard-disk-partition.html). Therefore it is worth to consider where to place such temporary files.  
  
 Locations to place temporary files:

- Secondary partition, this will lower the chance of file fragmentation on the primary partition.
- Secondary HDD, this will lower the burden and fragmentation on the primary HDD.
- RAM-Drive, this will increase the speed of file operations and remove fragmentation (Though files will be lost a reboot).
 
 Different types of temporary files:
- The TEMP folder : [Controlling the temporary directory](/article/temporary-directory.html).
- The pagefile : [Configure the page file for best performance](/article/windows-page-file.html).
- Temporary Internet Files : [Controlling Internet Explorer's Temporary Files Cache](/article/ie-temporary-internet-files.html).
- Disk Intensive Programs.
 
 Note one should consider configuring Index-Service or AntiVirus-Service not to scan directories with temporary files as it increases the CPU load.  
  
 To create a RAM drive to store such files, one can use these free tools:
- DOS RAMDRIVE.SYS that have existed since DOS 3.3 (Included with Win9x and found here C:\\WINDOWS. MSDOSDRV.TXT explains how to use it [MS KB142546](http://support.microsoft.com/kb/142546 "How to Use a RAM Drive to Troubleshoot Memory [Q142546]")).
- [XMSDSK](http://www.uwe-sieber.de/util_e.html) is an extended version of RAMDRIVE.SYS for Win9x (DOS), which makes it possible to specify which drive to use for RAM-drive.
- [ReSizeable RAMDisk](http://sourceforge.net/projects/srdisk) is an extended version of RAMDRIVE.SYS for Win9x (DOS), which allows one to resize the RAM drive on the fly.
- [MS KB257405](http://support.microsoft.com/kb/257405 "FILE: Ramdisk.sys Sample Driver for Windows 2000 [Q257405]") Win2k experimental Ramdisk.sys ([Ramdisk with GUI controls](http://www.ramdisk.tk/ "Christiaan Ghijselinck")).
- [MS WinNT4 DDK RAMDRIVE](http://smallvoid.orgfree.com/?file=ramdrvnt.zip) WinNT4 experimental RAMDRIVE.SYS.
- [PPSoft RAMDisk](http://www.ppsoft.dk/Ramdisk_Eng.htm) supports 95, 98, Me and 2000/XP (The download link is below the menu).
- [AR RAM Disk](http://www.arsoft-online.de/index.php?Itemid=30) it supports 2000/XP.
- [Christiaan Ghijselinck RAMDisk](http://www.ramdisk.tk/) supports 2k, XP and 2k3.
- [Dataram RAMDisk](http://memory.dataram.com/products-and-services/software/ramdisk?) - Supports 32 bit/64 bit Windows 2000-7.
 
 There is also the RAM drives you can pay for: - [www.superspeed.com](http://www.superspeed.com/) for NT and 2k.
- [www.virtusoft.com](http://www.virtusoft.com/) for 9x.
- [www.jlajoie.com](http://www.jlajoie.com/) for NT, 2K and 9x.
 
 Related [Configure cleanup profiles to remove unnecessary files](/article/cleanup-profiles.html)