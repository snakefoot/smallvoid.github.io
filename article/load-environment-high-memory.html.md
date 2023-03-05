---
title: 'Load environment in high memory with DOS 7.0'
date: '2000-01-01T15:13:02+01:00'
status: publish
permalink: /article/load-environment-high-memory.html
author: Snakefoot
excerpt: 'Load DOS environment in the upper memory block to free conventional memory.'
type: post
id: 42
category:
    - 'Tweak Performance'
tag:
    - config-sys
    - conventional-memory
    - high-memory-area
    - upper-memory-block
post_format: []
tags:
    - 'upper-memory-block,high-memory-area,conventional-memory,config-sys'
---
DOS 7.0 (Released with Windows 95) and later versions are able to load the following CONFIG.SYS environment parameters in the [Upper Memory Block (UMB)](/article/upper-memory-block-umb.html) and free conventional memory.  
  
 The STACKS setting determines the number(0,8-64) and size(32-512) of the stack spaces that are created to handle interrupt handling in real mode (Note if set too low it can cause stack overflow in Windows) - Default Value 9,256.
 > STACKSHIGH=9,256

 The LASTDRIVE setting specifies how many driveletters(A-Z) available to a DOS programn - Default your last drive letter.
 > LASTDRIVEHIGH=Z

 The FILES setting sets the number of File Handles(8-255) available to a DOS program to have open - Default value 30.
 > FILESHIGH=40

 The BUFFERS sets the number of disk buffers(1-99) available for limited buffering of file input/output (I/O) that is handled by MS-DOS real-mode drivers - Default value 30.
 > BUFFERSHIGH=40

 The FCBS (File Control BlockS) setting specifies the number of FCBS(1-255) available to a DOS program, but most DOS programs uses filehandles - Default value 4,0.
 > FCBSHIGH=1,0

 More Info [MS KB82318](http://support.microsoft.com/kb/82318 "Stack Overflow Can Cause Windows to Hang [Q82318]")  
 More Info [MS KB145799](http://support.microsoft.com/kb/145799 "How to Troubleshoot Windows Internal Stack Overflow Error Messages [Q145799]")  
 More Info [MS KB274646](http://support.microsoft.com/kb/274646 "Understanding the Settings in the Windows Millennium Edition Config.sys File [Q274646]")  