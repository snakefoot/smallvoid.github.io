---
title: 'Use extract.exe to restore a system file'
date: '2003-01-10T01:25:47+01:00'
permalink: /article/win9x-extract-restore.html
author: Snakefoot
excerpt: 'How use the extract utility for restoring a file from the Windows install CD.'
type: post
id: 180
categories:
    - windows-95_troubleshoot
    - windows-98_troubleshoot
    - windows-me_troubleshoot
tags:
    - backup
    - cab
    - command-line-switches
    - compress
    - extract
    - restore
---
Example to restore kernel32.dll to C:\\Windows\\System from the cabs files in D:\\Install

> extract D:\\Install\\Win95\_18.cab kernetl32.dll /L C:\\Windows\\System

 Instead of "guessing" which cab-file contains the file one can use a [for loop](/article/for-operation-files.html):
 > for %x in (D:\\Install\\\*.cab) do extract %x kernel32.dll /L C:\\Windows\\System

 Note instead of the for loop one can also try to use the extract /a switch and use the first cab-file in the series, though it will only work on cab-files which are chained together. To see all command line switches execute extract with no parameters.  
  
 Note one can also use extract.exe to restore from cab files for Internet Explorer.  
  
 Related [Win98: Use SFC.EXE to restore a system file](/article/win98-sfc.html)  
 Related [WinMe: Use Msconfig.exe to restore a system file](/article/winme-system-restore.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+129605+Q129605" rel="nofollow" title="HOW TO: Extract Original Compressed Windows Files [Q129605]">MS KB129605</a>  