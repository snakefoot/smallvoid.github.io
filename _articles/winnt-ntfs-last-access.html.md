---
title: 'Disable the automatic updating of file access time'
date: '2000-01-01T13:55:48+01:00'
permalink: /article/winnt-ntfs-last-access.html
author: Snakefoot
excerpt: 'Lower the disk activity by disabling the updating of when a file was last accessed.'
type: post
id: 26
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-nt4_performance
    - windows-xp_performance
    - windows-vista_performance
tags:
    - disk-performance
    - file-access-time
    - file-system
    - ntfs
---
When a file is opened then the last access timestamp for the file is updated. This timestamp can be useful for applications that detects, whether certain files have been used recently. If not using such applications, then one might consider disabling the updating of this timestamp, to make file operations quicker.  
  
 Configure the following DWORD registry key (Only affects NTFS partitions):

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  NtfsDisableLastAccessUpdate=1 (Default = 0, Vista Default = 1)

 Note the utility fsutil can also be used to change this value:
 > fsutil behavior set disablelastaccess 1

 More Info <a href="https://www.bing.com/search?q=KB+150355+Q150355" rel="nofollow" title="Windows NT Nonresponsive during NTFS Directory Traversal [Q150355]">MS KB150355</a>  