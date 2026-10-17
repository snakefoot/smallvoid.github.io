---
title: 'Disable paging of drivers and kernel core'
date: '2000-01-01T21:31:26+01:00'
permalink: /article/winnt-core-paging.html
author: Snakefoot
excerpt: 'Prevent the Windows kernel core from being paged to disk.'
type: post
id: 369
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-nt4_performance
    - windows-xp_performance
tags:
    - kernel
    - page-file
---
There is an option to force the kernel core and drivers to stay in RAM (non-pageable) and not [swap to the harddisk](/article/windows-page-file.html). When the option is enabled, then it will lock a "large" amount of RAM, that the paging algorithm cannot touch, even if it might be able to make a more optimal use of the RAM.  
  
 By default it is possible for the kernel core and the drivers to mark themselves as non-pageable, so it is only in rare situations that one should force all to become non-pageable. If having plenty of RAM available then this option doesn't make any difference, as it will have no need to page out the kernel core and drivers.  
  
 This setting is useful for debugging drivers as it ensures that all kernel code and data is always memory resident. Also on 64 bit Windows by forcing the kernel into RAM, then it will allow proper kernel stack traces.  
  
 To force the core into RAM edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  DisablePagingExecutive = 1 (1 = Force to RAM, 0 = Allow to page, Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20184419%20Q184419" rel="nofollow" title="How to Stop the NTExecutive from Paging to Disk [Q184419]">MS KB184419</a>

 Note until Win2k SP4 a flaw existed which could cause the system to hang when this registry entry was enabled. More Info <a href="https://www.bing.com/search?q=KB%20323608%20Q323608" rel="nofollow" title="The DisablePagingExecutive Setting May Cause Windows 2000 to Hang [Q323608]">MS KB323608</a>  
  
 Credits [ArsTechnica.com](http://arstechnica.com/)