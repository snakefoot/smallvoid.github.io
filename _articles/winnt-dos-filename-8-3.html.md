---
title: 'Disable creation of DOS compatible 8.3 filename'
date: '2000-01-01T13:47:30+01:00'
permalink: /article/winnt-dos-filename-8-3.html
author: Snakefoot
excerpt: 'Speed up the creation of new files by not creating a 8.3 filename for backward compatibility.'
type: post
id: 25
categories:
    - windows-2000_performance
    - windows-2003_performance
    - windows-nt4_performance
    - windows-xp_performance
    - windows-vista_performance
tags:
    - disk-performance
    - file-system
    - ntfs
---
When a file is created a filename is attached to actual contents of the file. For the sake of compatibility, then a 8.3 filename is created along with the long filename. If running applications that creates many files, then they might show better performance if one disables the generation of the 8.3 filename.  
  
 To do this edit this DWORD registry key: (Only affects NTFS partitions)

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  NtfsDisable8dot3NameCreation=1

 Note the utility fsutil can also be used to change this value:
 > fsutil behavior set disable8dot3 1

 Note that original Windows 95 without SP1 will not be able to access files created.  
  
 Note that some applications still uses 8.3 filenames, and might fail to function (Ex. applications running at boot time ex. virus scanners or similar).  
  
 More Info <a href="https://www.bing.com/search?q=KB%20121007%20Q121007" rel="nofollow" title="How to Disable the 8.3 Name Creation on NTFS Partitions [Q121007]">MS KB121007</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20130694%20Q130694" rel="nofollow" title="NTFS Performance with Numerous Long Filenames [Q130694]">MS KB130694</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20142982%20Q142982" rel="nofollow" title="How Windows Generates 8.3 File Names from Long File Names [Q142982]">MS KB142982</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20183387%20Q183387" rel="nofollow" title="Err Msg: Unable to Determine or Construct a Path for the Program Files Folder [Q183387]">MS KB183387</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20210638%20Q210638" rel="nofollow" title="How to Disable Automatic Short File Name Generation [Q210638]">MS KB210638</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20226403%20Q226403" rel="nofollow" title="Short (8.3) File Names May Change When Copied [Q226403]">MS KB226403</a>  