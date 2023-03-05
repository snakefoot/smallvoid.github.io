---
title: 'Disable paging of drivers and kernel core'
date: '2000-01-01T21:31:26+01:00'
status: publish
permalink: /article/winnt-core-paging.html
author: Snakefoot
excerpt: 'Prevent the Windows kernel core from being paged to disk.'
type: post
id: 369
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - kernel
    - page-file
post_format: []
tags:
    - 'page-file,kernel'
---
There is an option to force the kernel core and drivers to stay in RAM (non-pageable) and not [swap to the harddisk](/article/windows-page-file.html). When the option is enabled, then it will lock a "large" amount of RAM, that the paging algorithm cannot touch, even if it might be able to make a more optimal use of the RAM.  
  
 By default it is possible for the kernel core and the drivers to mark themselves as non-pageable, so it is only in rare situations that one should force all to become non-pageable. If having plenty of RAM available then this option doesn't make any difference, as it will have no need to page out the kernel core and drivers.  
  
 This setting is useful for debugging drivers as it ensures that all kernel code and data is always memory resident. Also on 64 bit Windows by forcing the kernel into RAM, then it will allow proper kernel stack traces.  
  
 To force the core into RAM edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  DisablePagingExecutive = 1 (1 = Force to RAM, 0 = Allow to page, Default = 0)  
>   
>  More Info [MS KB184419](http://support.microsoft.com/kb/184419 "How to Stop the NTExecutive from Paging to Disk [Q184419]")

 Note until Win2k SP4 a flaw existed which could cause the system to hang when this registry entry was enabled. More Info [MS KB323608](http://support.microsoft.com/kb/323608 "The DisablePagingExecutive Setting May Cause Windows 2000 to Hang [Q323608]")  
  
 Credits [ArsTechnica.com](http://arstechnica.com/)