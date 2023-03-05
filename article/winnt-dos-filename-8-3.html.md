---
title: 'Disable creation of DOS compatible 8.3 filename'
date: '2000-01-01T13:47:30+01:00'
status: publish
permalink: /article/winnt-dos-filename-8-3.html
author: Snakefoot
excerpt: 'Speed up the creation of new files by not creating a 8.3 filename for backward compatibility.'
type: post
id: 25
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
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
When a file is created a filename is attached to actual contents of the file. For the sake of compatibility, then a 8.3 filename is created along with the long filename. If running applications that creates many files, then they might show better performance if one disables the generation of the 8.3 filename.  
  
 To do this edit this DWORD registry key: (Only affects NTFS partitions)

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  NtfsDisable8dot3NameCreation=1

 Note the utility fsutil can also be used to change this value:
 > fsutil behavior set disable8dot3 1

 Note that original Windows 95 without SP1 will not be able to access files created.  
  
 Note that some applications still uses 8.3 filenames, and might fail to function (Ex. applications running at boot time ex. virus scanners or similar).  
  
 More Info [MS KB121007](http://support.microsoft.com/kb/121007 "How to Disable the 8.3 Name Creation on NTFS Partitions [Q121007]")  
 More Info [MS KB130694](http://support.microsoft.com/kb/130694 "NTFS Performance with Numerous Long Filenames [Q130694]")  
 More Info [MS KB142982](http://support.microsoft.com/kb/142982 "How Windows Generates 8.3 File Names from Long File Names [Q142982]")  
 More Info [MS KB183387](http://support.microsoft.com/kb/183387 "Err Msg: Unable to Determine or Construct a Path for the Program Files Folder [Q183387]")  
 More Info [MS KB210638](http://support.microsoft.com/kb/210638 "How to Disable Automatic Short File Name Generation [Q210638]")  
 More Info [MS KB226403](http://support.microsoft.com/kb/226403 "Short (8.3) File Names May Change When Copied [Q226403]")  