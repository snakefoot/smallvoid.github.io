---
title: 'Windows 98 regedit'
date: '2003-03-01T01:13:46+01:00'
permalink: /article/win95-regedit.html
author: Snakefoot
excerpt: 'Modified version of Windows 98 regedit, which can be used in Windows 95.'
type: post
id: 164
categories:
    - windows-95_utilities
tags:
    - regedit
    - registry
---
[Windows 98 regedit](http://smallvoid.orgfree.com/?file=regedit.zip) modified to work with Windows 95 so it can <a href="https://www.bing.com/search?q=KB+132064+Q132064" title="REGEDIT May Not Be Able to Import Registry with Large Keys [Q132064]" rel="nofollow">handle large registry keys</a> in realmode (DOS).  
  
 When a Windows installation have been running for a long time and hardware, software have been changed alot, then the registry can become bloated. One can use REGEDIT in DOS to compress/shrink the registry.  
  
 Exit to DOS and write the following command to extract both system.dat and user.dat to the file all.reg:
> cd c:\\windows  
> regedit /e all.reg

 When it is finished write the following command to restore both system.dat and user.dat from the file all.reg:
 > regedit /c all.reg

 Note one can speed up the process by loading [SMARTDRV](/article/hdd-disk-cache-smartdrv.html) before hand.  
  
 Note it can be a good idea to make a backup of the system.dat and user.dat before starting this process.  
  
 Note this can also be used to change the registry in DOS by editing the All.reg with Edit.exe.  
  
 Note if using Win98/Me one can just use [SCANREG](/article/win9x-registry-checker.html).  
  
 More Info <a href="https://www.bing.com/search?q=KB%20131352%20Q131352" rel="nofollow" title="Using Registry Editor in Real Mode [Q131352]">MS KB131352</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20131431%20Q131431" rel="nofollow" title="How to Troubleshoot Registry Errors in Windows 95 [Q131431]">MS KB131431</a>  