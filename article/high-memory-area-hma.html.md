---
title: 'Open access to the High Memory Area (HMA)'
date: '2000-01-01T14:47:46+01:00'
status: publish
permalink: /article/high-memory-area-hma.html
author: Snakefoot
excerpt: 'Description of the High Memory Area (HMA), and how to open access to it with Himen.sys to free conventional memory.'
type: post
id: 39
category:
    - 'Tweak Performance'
tag:
    - config-sys
    - high-memory-area
    - himem-sys
post_format: []
tags:
    - 'high-memory-area,himem-sys,config-sys'
---
The High Memory Area (HMA) is the first 64 KByte after the first 1024 Kbyte (Conventional+UMA).

<table border="1" cellpadding="2" cellspacing="2"><tr align="center"><th>Memory</th><th>Size</th><th>Provider</th></tr><tr align="center"><td>XMS/[EMS](/article/expanded-memory-ems-extended-memory-xms.html)</td><td>? K</td><td>Himem.sys/Emm386.exe</td></tr><tr align="center"><td>HMA</td><td>64K</td><td>Himem.sys</td></tr><tr align="center"><td>[UMA/UMB](/article/upper-memory-block-umb.html)</td><td>384K</td><td>Emm386.exe</td></tr><tr align="center"><td>Conventional</td><td>640K</td><td> </td></tr></table>

 It is possible to load some of the DOS environment into the HMA and free up some conventional memory.  
  
 Edit CONFIG.SYS and update/insert these lines:
 
>  DEVICE=C:\\DOS\\HIMEM.SYS  
>  DOS=HIGH

 Note the HIMEM.SYS is a driver that forfills the eXtended Memory Specification (XMS), which specifies how to allocate memory beyond the first 1024 KByte and therefore also the HMA. The memory beyond the HMA is called extended memory or just XMS.  
  
 More Info [MS KB91088](http://support.microsoft.com/kb/91088 "HIMEM.SYS Memory Allocation Scheme [91088]")  
 More Info [MS KB72302](http://support.microsoft.com/kb/72302 "Specifying A20 Handlers with HIMEM.SYS /M in MS-DOS [Q72302]")  
 More Info [MS KB96711](http://support.microsoft.com/kb/96711 "HIMEM.SYS Reports Error: Unable to Control A20 Line! [96711]")  
 More Info [MS KB105557](http://support.microsoft.com/kb/105557 "HIMEM.SYS Verbose and Quiet Switches [Q105557]")  