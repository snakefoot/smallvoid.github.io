---
title: 'Specify the size of the 2nd level on the CPU'
date: '2000-01-01T14:00:36+01:00'
permalink: /article/winnt4-second-level-cache.html
author: Snakefoot
excerpt: 'Windows has trouble with determining the size of the second level cache for older CPU''s.'
type: post
id: 27
categories:
    - windows-nt4_performance
tags:
    - cpu
    - cpu-cache
---
With older CPUs the HAL(Hardware Abstraction Layer) cannot detect the correct amount of 2nd level cache, which is the case with Pentium 1 using direct-mapped L2 cache (And sets it to default 256 KB).  
  
 To force usage of a certain amount of 2nd level cache in KBytes, edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager \\Memory Management\]  
>  SecondLevelDataCache=512 (Default AutoDetect - 0)

 Note newer processors like the AMD K6-2 and Pentium2 are using set-associative 2nd Level cache and are detected properly. Force setting the second level cache for such CPUs (And newer) will probably do more harm than good.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20183063%20Q183063" rel="nofollow" title="Detailed Explanation of SecondLevelDataCache [Q183063]">MS KB183063</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20228766%20Q228766" rel="nofollow" title="How to Change the Server Service Properties [Q228766]">MS KB228766</a>  
  
 Credits [arstechnica.com](http://www.arstechnica.com/)