---
title: 'Open access to the Upper Memory Block (UMB)'
date: '2000-01-01T14:56:22+01:00'
status: publish
permalink: /article/upper-memory-block-umb.html
author: Snakefoot
excerpt: 'Description of the Upper Memory Block (UMB) and how to open access to it with Emm386.exe.'
type: post
id: 40
category:
    - 'Tweak Performance'
tag:
    - conventional-memory
    - emm386
    - high-memory-area
    - himem-sys
    - upper-memory-area
    - upper-memory-block
post_format: []
tags:
    - 'high-memory-area,upper-memory-block,upper-memory-area,conventional-memory,himem-sys,emm386'
---
To get access to the Upper Memory Block (UMB) which is allocated from the upper memory area (UMA) one have to load the Expanded Memory Manager EMM386.EXE. The UMA covers 384 KByte and is placed just above the 640 Kbyte conventional memory. The UMB cannot occupy the entire UMA as other things resides there.  
  
 Edit the CONFIG.SYS and update/insert these lines to access the UMB:

> DEVICE=C:\\DOS\\HIMEM.SYS  
>  DEVICE=C:\\DOS\\EMM386.EXE  
>  DOS=HIGH,UMB

 If not using [expanded memory](/article/expanded-memory-ems-extended-memory-xms.html) then free 64Kbyte UMB:
> DEVICE=C:\\DOS\\HIMEM.SYS  
>  DEVICE=C:\\DOS\\EMM386.EXE NOEMS  
>  DOS=HIGH,UMB

 There is allocated memory for Monochrome support in the UMA, but it can be included in the UMB instead:
> DEVICE=C:\\DOS\\HIMEM.SYS  
>  DEVICE=C:\\DOS\\EMM386.EXE NOEMS I=B000-B7FF  
>  DOS=HIGH,UMB

 Use HIGHSCAN in DOS 6.0+ to scan aggressively for UMB in the UMA (Can cause trouble):
> DEVICE=C:\\DOS\\HIMEM.SYS  
>  DEVICE=C:\\DOS\\EMM386.EXE I=B000-B7FF NOEMS HIGHSCAN  
>  DOS=HIGH,UMB

 Note if wanting better memory performance then one should take a closer look at [UMBPCI.SYS](http://www.uwe-sieber.de/umbpci_e.html), which is an Expanded Memory Manager that has been optimized for several motherboard chipsets.  
  
 Related [Load drivers in high memory to save conventional memory](/article/load-drivers-high-memory.html)  
 Related [Load environment in high memory with DOS 7.0](/article/load-environment-high-memory.html)  
  
 More Info [MS KB37242](http://support.microsoft.com/kb/37242 "A General Tutorial on the Various Forms of Memory [Q37242]")  
 More Info [MS KB77083](http://support.microsoft.com/kb/77083 "Optimizing Your Use of Upper Memory Blocks [Q77083]")  
 More Info [MS KB78557](http://support.microsoft.com/kb/78557 "EMM386 Troubleshooting and Technical Information [Q78557]")  
 More Info [MS KB98508](http://support.microsoft.com/kb/98508 "EMM386.EXE B=<address> Explained [Q98508]")  
 More Info [MS KB78433](http://support.microsoft.com/kb/78433 "Detailed Explanation of EMM386.EXE Switches [Q78433]")  
 More Info [MS KB93375](http://support.microsoft.com/kb/93375 "Changes in EMM386.EXE Version 4.45 (MS-DOS 6.0) [Q93375]")  
 More Info [MS KB112816](http://support.microsoft.com/kb/112816 "Locating and Excluding RAM/ROM Addresses in the UMA [Q112816]")  