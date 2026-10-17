---
title: 'Open access to the High Memory Area (HMA)'
date: '2000-01-01T14:47:46+01:00'
permalink: /article/high-memory-area-hma.html
author: Snakefoot
excerpt: 'Description of the High Memory Area (HMA), and how to open access to it with Himen.sys to free conventional memory.'
type: post
id: 39
categories:
    - ms-dos_performance
tags:
    - config-sys
    - high-memory-area
    - himem-sys
---
The High Memory Area (HMA) is the first 64 KByte after the first 1024 Kbyte (Conventional+UMA).

- [XMS/EMS](/article/expanded-memory-ems-extended-memory-xms.html) (Himem.sys/Emm386.exe)
- HMA - 64K (Himem.sys)
- [UMA/UMB](/article/upper-memory-block-umb.html) - 384K (Emm386.exe)
- Conventional - 640K

 It is possible to load some of the DOS environment into the HMA and free up some conventional memory.  
  
 Edit CONFIG.SYS and update/insert these lines:
 
>  DEVICE=C:\\DOS\\HIMEM.SYS  
>  DOS=HIGH

 Note the HIMEM.SYS is a driver that forfills the eXtended Memory Specification (XMS), which specifies how to allocate memory beyond the first 1024 KByte and therefore also the HMA. The memory beyond the HMA is called extended memory or just XMS.  
  
 More Info <a href="https://www.bing.com/search?q=KB%2091088%20Q91088" rel="nofollow" title="HIMEM.SYS Memory Allocation Scheme [91088]">MS KB91088</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2072302%20Q72302" rel="nofollow" title="Specifying A20 Handlers with HIMEM.SYS /M in MS-DOS [Q72302]">MS KB72302</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2096711%20Q96711" rel="nofollow" title="HIMEM.SYS Reports Error: Unable to Control A20 Line! [96711]">MS KB96711</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20105557%20Q105557" rel="nofollow" title="HIMEM.SYS Verbose and Quiet Switches [Q105557]">MS KB105557</a>  