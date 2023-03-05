---
title: 'Using smart drive for faster boot time'
date: '2003-08-09T00:17:51+02:00'
status: publish
permalink: /article/win9x-smartdrv.html
author: Snakefoot
excerpt: 'Optimize the boot time of Windows by using the DOS disk cache until the Windows disk cache takes over.'
type: post
id: 103
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - boot-time
    - disk-performance
    - file-cache
    - smartdrv
post_format: []
tags:
    - 'smartdrv,file-cache,boot-time,disk-performance'
---
It is possible to cut down on the time to boot Windows by loading a disk cache like [SmartDrv](/article/hdd-disk-cache-smartdrv.html). The good thing about SmartDrv is that it can be configured to use a minimal amount of memory when inside Windows.  
  
 To create a 2 Mbyte disk cache while loading Windows and only use 16 Kbyte (WinCacheSize) when inside Windows, add the following line to your AUTOEXEC.BAT:

> LOADHIGH C:\\Windows\\SmartDrv.exe 2048 16

 Note if it takes a long time to boot Win9x then it is usually caused by misconfigured hardware devices. To detect such devices use [Boot Log Analyzer](/article/win9x-boot-log-analyzer.html).  
  
 Related [Remove ghost devices to make the boot time faster](/article/win9x-ghost-devices.html)  
 Related [Faster boot times by using static IP instead of DHCP](/article/dhcp-static-ip.html)  
 Related [Faster boot by loading DOS drivers at Windows exit](/article/win9x-dosstart.html)  
  
 Credits [www.mdgx.com](http://www.mdgx.com/)