---
title: 'Configure the disk cache to improve disk performance'
date: '2000-01-01T19:03:35+01:00'
status: publish
permalink: /article/win9x-disk-cache.html
author: Snakefoot
excerpt: 'How to configure the disk cache for faster file operations.'
type: post
id: 89
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-cache
    - hard-disk-drive
post_format: []
tags:
    - 'file-cache,hard-disk-drive,disk-performance'
---
To avoid accessing the HDD every time to read a file, it caches the most used files or at least the most used parts of the file. The RAM allocated for disk cache cannot be used by applications, so if having a limited amount of RAM one should consider the amount of memory used for disk caching.  
  
 Edit the file C:\\Windows\\System.ini and find the section **\[vcache\]** and write the following:

> \[vcache\]  
>  MaxFileCache = 8192  
>  MinFileCache = 1024  
>  ChunkSize = 512

 The above values means that it will take 8192 KByte of your memory to use for the virtual disk cache. The memory will be allocated in chunks of 512 KByte.  
  
 One can use the following table to find a suitable value: <table border="1" cellpadding="5"><tr><th>Installed RAM</th> <th>MaxFileCache</th> <th>MinFileCache</th> <th>ChunkSize</th></tr><tr><td>32 Mbyte</td> <td>2048</td> <td>1024</td> <td>512</td></tr><tr><td>64 Mbyte</td> <td>4096</td> <td>1024</td> <td>512</td></tr><tr><td>128 Mbyte</td> <td>8192</td> <td>1024</td> <td>512</td></tr><tr><td>256+ Mbyte</td> <td>32768</td> <td>4096</td> <td>1024</td></tr></table>

 More Info [MS KB108079](http://support.microsoft.com/kb/108079 "32-Bit File Access Maximum Cache Size [Q108079]")  
 More Info [MS KB225497](http://support.microsoft.com/kb/225497 "PRB: Windows 95 May Fail to Boot Due to I/O Subsystem Failure [Q225497]")  