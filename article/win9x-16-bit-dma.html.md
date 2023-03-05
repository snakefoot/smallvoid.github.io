---
title: 'Improve 16 bit DMA transfers by increasing DMA buffer size'
date: '2001-01-01T21:55:41+01:00'
status: publish
permalink: /article/win9x-16-bit-dma.html
author: Snakefoot
excerpt: 'How to configure the size of the pre-allocated DMA buffer for use by 16 bit applications.'
type: post
id: 97
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - dma
post_format: []
tags:
    - dma
---
Windows 9x is able to run 16 bit programs, and when they attempt to allocate DMA buffers to perform Direct Memory Access (DMA) transfers they are limited to the pre-allocated DMA buffer (with double buffering), unless they can provide a physically contiguous memory allocation themselves.  
  
 To configure the size of the pre-allocated DMA buffer, add this line in the file SYSTEM.INI in the section \[386Enh\]:

> \[386Enh\]  
>  DMABufferSize=64 (Default - 16 Range 1-256)

 More Info [MS KB82711](http://support.microsoft.com/kb/82711 "How EMM386 and Windows 3.1 Relate [Q82711]")  
 More Info [MS KB82790](http://support.microsoft.com/kb/82790 "SYSTEM.INI's NetDMASize= Switch and NetBIOS [Q82790]")  
 More Info [MS KB124729](http://support.microsoft.com/kb/124729 "How to Program DMA Transfers in the Protected Mode Windows Env [Q124729]")  
  
 Note the above setting can also be configured by going to the "Control Panel" -&gt; "System" -&gt; "Device Manager", and expand the "System"-node, and select properties for "Direct Memory Access Controller", and select the tab "Settings" and set the "Reserve DMA buffer" to 64.