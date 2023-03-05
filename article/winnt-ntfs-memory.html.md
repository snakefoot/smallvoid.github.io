---
title: 'Configure the memory usage of the NTFS file system'
date: '2005-09-25T01:44:36+02:00'
status: publish
permalink: /article/winnt-ntfs-memory.html
author: Snakefoot
excerpt: 'How to increase the amount of memory the NTFS filesystem can use for file operations.'
type: post
id: 378
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-system
    - ntfs
post_format: []
tags:
    - 'ntfs,disk-performance'
---
The NTFS file system have a limited pool of kernel-buffers (lookaside list), which are used when doing file operations ex. a larger read-ahead cache. If there are so many file operations (read/write files), that all the buffers are used up, then it will block for new file operations until an active one have completed.  
  
 It is possible to increase the memory usage, so it can handle more concurrent file operations:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  NtfsMemoryUsage = 1 (Normal = 1, Increased = 2; Default = 1)

 Note the utility fsutil can also be used to change this value:
> fsutil behavior set memoryusage 2  
>   
>  More Info [MS TechCenter - Fsutil: behavior](http://technet2.microsoft.com/WindowsServer/en/Library/9fcf44c8-68f4-4204-b403-0282273bc7b31033.mspx)

 Note this setting is mainly for server systems with a high end disk system that consists of multiple disks, which is bombarded with file operations (Like a Web-Server).  
  
 Note when increasing the memory usage, then it will use more of both [paged- and non-paged-memory](/article/winnt-kernel-memory.html). Therefore make sure that existing services/drivers are not already using the available paged and non-paged memory, as these services might perform worse with less memory available.