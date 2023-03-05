---
title: 'Increase HDD speed with disk cache'
date: '2000-01-01T15:45:44+01:00'
status: publish
permalink: /article/hdd-disk-cache-smartdrv.html
author: Snakefoot
excerpt: 'Description of how a disk cache will help HDD performance, and how to activate the smart drive disk cache.'
type: post
id: 44
category:
    - 'Tweak Performance'
tag:
    - autoexec-bat
    - disk-performance
    - file-cache
    - file-system
    - smartdrv
post_format: []
tags:
    - 'file-system,file-cache,smartdrv,autoexec-bat,disk-performance'
---
Smart Drive (SMARTDRV) is a disk cache driver, which creates a disk cache in the extended memory. When a program requests data from the HDD or CDROM the data is also copied to the disk cache, so if the program asks for the data again then it will not require to access the slow HDD or CDROM. When a program reads a file then it usually process it in small chunks. While the program is processing a single chunk, then the disk cache is able to read-ahead several small chunks of the file and have them ready in memory.  
  
 Edit AUTOEXEC.BAT and update/insert this line:

> C:\\Dos\\Smartdrv.exe 2048

 Note if loading MSCDEX.EXE for CD-ROM support, then load SMARTDRV after MSCDEX.EXE so the CD-Drives also gets a diskcache.  
  
 Note smart drive can also be loaded into the [Upper Memory Block](/article/load-drivers-high-memory.html) to free conventional memory.  
  
 More Info [MS KB81377](http://support.microsoft.com/kb/81377 "SMARTDrive /double_buffer Cannot Load into UMBs [Q81377]")  
 More Info [MS KB81607](http://support.microsoft.com/kb/81607 "Rebooting from a Batch File with SMARTDRV.EXE Loaded [Q81607]")  
 More Info [MS KB82709](http://support.microsoft.com/kb/82709 "SMARTDRV Cache Status -- What Does the Buffering Value Mean? [Q82709]")  
 More Info [MS KB83376](http://support.microsoft.com/kb/83376 "SMARTDrive ElementSize Should Precede CacheSizes [Q83376]")  
 More Info [MS KB84706](http://support.microsoft.com/kb/84706 "Troubleshooting SMARTDrive Version 4.0 [Q84706]")  
 More Info [MS KB95531](http://support.microsoft.com/kb/95531 "SMARTDrive: Maximum Cache Size [Q95531]")  
 More Info [MS KB241458](http://support.microsoft.com/kb/241458 "HOWTO: Speed the Preinstallation Process for Windows 9x [Q241458]")  