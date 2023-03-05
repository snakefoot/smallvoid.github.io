---
title: 'Emulate expanded memory (EMS) by using extended memory (XMS)'
date: '2000-01-01T15:02:46+01:00'
status: publish
permalink: /article/expanded-memory-ems-extended-memory-xms.html
author: Snakefoot
excerpt: 'Description of the Expanded Memory Specification (EMS) and how to use Emm386.exe to emulate XMS as EMS.'
type: post
id: 41
category:
    - 'Tweak Performance'
tag:
    - config-sys
    - emm386
    - expanded-memory
    - extended-memory
    - himem-sys
post_format: []
tags:
    - 'expanded-memory,extended-memory,himem-sys,emm386,config-sys'
---
The Expanded Memory Manager EMM386.EXE can be configured to allocate the memory beyond the 1 MByte according to the expanded memory specification (EMS) instead of the eXtended memory Specification (XMS). This is useful when running games and programs that requires expanded memory.  
  
 Edit CONFIG.SYS and update/insert these lines to emulate 1 Mbyte XMS as EMS:

> DEVICE=C:\\DOS\\HIMEM.SYS  
>  DEVICE=C:\\DOS\\EMM386.EXE 1024 RAM  
>  DOS=HIGH,UMB

 Note that the parameter "RAM" will of course not work together with the "NOEMS" parameter. When using the "RAM" parameter 64 KByte of the [Upper Memory Block (UMB)](/article/upper-memory-block-umb.html) will be taken.  
  
 More Info [MS KB76916](http://support.microsoft.com/kb/76916 "Size of Expanded Memory Pool Adjusted [Q76916]")  
 More Info [MS KB96759](http://support.microsoft.com/kb/96759 "No Expanded Memory Available After Installing EMM386.EXE [Q96759]")  
 More Info [MS KB275423](http://support.microsoft.com/kb/275423 "Cannot Configure Expanded Memory Support for an MS-DOS-Based Program [Q275423]")  