---
title: 'Disable Page Size Extension for AMD Athlon XP'
date: '2001-01-01T23:59:51+01:00'
status: publish
permalink: /article/winnt-large-page-minimum.html
author: Snakefoot
excerpt: 'Configure the Page Size Extension feature of the processor which is used to for activate large pages support.'
type: post
id: 466
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - AGP
    - AMD
    - blue-screen-of-death
    - cpu
    - page-size-extension
post_format: []
tags:
    - 'page-size-extension,AMD,blue-screen-of-death,AGP,cpu'
---
AMD Ahtlon XP processors combined with AGP display adapters can cause blue screen of death (BSOD) along with Windows locking up or freezes.  
  
 By disabling Windows from using the Page Size Extension (PSE) feature of the CPU (Central Processor Unit), then these problems should disappear:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  LargePageMinimum = 0xffffffff  
>   
>  More Info [MS KB270715](http://support.microsoft.com/kb/270715 "AGP Program May Hang When Using Page Size Extension on Athlon Processor [270715]")

 Note disabling PSE will disable large pages (4 MB instead of 4K) but will enable write protection of the memory area for the kernel. Large pages increases address translation performance and makes it possible to use a single TLB (Translation Lookaside Buffer) to map 4 MByte of RAM and increases the [non-paged pool](/article/winnt-kernel-memory.html) limit to 256 MB (Instead of 128 MByte). The large pages are used to map the Windows core into memory like: NTOSKRNL, HAL, nonpaged pool, and the PFN database.