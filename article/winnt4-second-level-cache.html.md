---
title: 'Specify the size of the 2nd level on the CPU'
date: '2000-01-01T14:00:36+01:00'
status: publish
permalink: /article/winnt4-second-level-cache.html
author: Snakefoot
excerpt: 'Windows has trouble with determining the size of the second level cache for older CPU''s.'
type: post
id: 27
category:
    - 'Tweak Performance'
tag:
    - cpu
    - cpu-cache
post_format: []
tags:
    - 'cpu,cpu-cache'
---
With older CPUs the HAL(Hardware Abstraction Layer) cannot detect the correct amount of 2nd level cache, which is the case with Pentium 1 using direct-mapped L2 cache (And sets it to default 256 KB).  
  
 To force usage of a certain amount of 2nd level cache in KBytes, edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  SecondLevelDataCache=512 (Default AutoDetect - 0)

 Note newer processors like the AMD K6-2 and Pentium2 are using set-associative 2nd Level cache and are detected properly. Force setting the second level cache for such CPUs (And newer) will probably do more harm than good.  
  
 More Info [MS KB183063](http://support.microsoft.com/kb/183063 "Detailed Explanation of SecondLevelDataCache [Q183063]")  
 More Info [MS KB228766](http://support.microsoft.com/kb/228766 "How to Change the Server Service Properties [Q228766]")  
  
 Credits [arstechnica.com](http://www.arstechnica.com/)