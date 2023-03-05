---
title: 'Load drivers in high memory to free conventional memory'
date: '2000-01-01T15:20:09+01:00'
status: publish
permalink: /article/load-drivers-high-memory.html
author: Snakefoot
excerpt: 'How load drivers in the upper memory block to free conventional memory.'
type: post
id: 43
category:
    - 'Tweak Performance'
tag:
    - conventional-memory
    - device-driver
    - high-memory-area
    - terminate-stay-resident
    - upper-memory-block
post_format: []
tags:
    - 'high-memory-area,conventional-memory,upper-memory-block,terminate-stay-resident,device-driver'
---
If having opened access to the [Upper Memory Block (UMB)](/article/upper-memory-block-umb.html), then one can load CDROM-drivers and other Terminate and Stay Resident (TSR) programs like DOSKEY.EXE into the Upper Memory Block (UMB) to increase the available conventional memory.  
  
 Edit AUTOEXEC.BAT and use LH/LOADHIGH:

> LOADHIGH DOSKEY.EXE

 Edit CONFIG.SYS and use DEVICEHIGH:
 
 > DEVICEHIGH=C:\\CDROM\\DRIVER.SYS

 Note that if there is not enough free memory for the device to load in the UMB, then the device is loaded in the conventional memory. Therefore it might be a good idea to [Check how much memory each TSR program uses](/article/mem-conventional-memory.html) and then order the loading of the TSR programs so the UMB is packed completely.  
  
 More Info [MS KB151718](http://support.microsoft.com/kb/151718 "Managing Memory in MS-DOS Mode [Q151718]")  
 More Info [MS KB72183](http://support.microsoft.com/kb/72183 "Loading MS-DOS 5.0 TSRs and Device Drivers into UMBs [Q72183]")  
 More Info [MS KB96028](http://support.microsoft.com/kb/96028 "Using /S Switch with LOADHIGH [Q96028]")  
 More Info [MS KB95555](http://support.microsoft.com/kb/95555 "Overview of Memory-Management Functionality in MS-DOS [Q95555]")  
 More Info [MS KB76820](http://support.microsoft.com/kb/76820 "Programs Don't Load into Upper Memory Area [Q76820]")  