---
title: 'Windows 98 regedit'
date: '2003-03-01T01:13:46+01:00'
status: publish
permalink: /article/win95-regedit.html
author: Snakefoot
excerpt: 'Modified version of Windows 98 regedit, which can be used in Windows 95.'
type: post
id: 164
category:
    - Utilities
tag:
    - regedit
    - registry
post_format: []
tags:
    - 'regedit,registry'
---
[Windows 98 regedit](http://smallvoid.orgfree.com/?file=regedit.zip) modified to work with Windows 95 so it can [handle large registry keys](http://support.microsoft.com/kb/132064 "REGEDIT May Not Be Able to Import Registry with Large Keys [Q132064]") in realmode (DOS).  
  
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
  
 More Info [MS KB131352](http://support.microsoft.com/kb/131352 "Using Registry Editor in Real Mode [Q131352]")  
 More Info [MS KB131431](http://support.microsoft.com/kb/131431 "How to Troubleshoot Registry Errors in Windows 95 [Q131431]")  