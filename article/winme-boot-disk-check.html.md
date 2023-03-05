---
title: 'Running Scandisk in Windows Me after improper shutdown'
date: '2001-01-01T00:42:49+01:00'
status: publish
permalink: /article/winme-boot-disk-check.html
author: Snakefoot
excerpt: 'Windows Me will perform a scandisk after an improper shutdown when Windows has started up.'
type: post
id: 175
category:
    - Troubleshoot
tag:
    - hard-disk-drive
    - scandisk
post_format: []
tags:
    - 'scandisk,hard-disk-drive'
---
If Windows Me has experienced an improper/incorrect shutdown, then it will check the hard disk to correct any errors caused by the premature shutdown.  
  
 Instead of running the Scandisk in DOS realmode like in Win95/98, then in WinMe the Scandisk is launched after having booted to Windows. One can still disable the launch of Scandisk, but instead of [AutoScan in the Msdos.sys](/article/win9x-msdos-sys.html), then it is a BINARY key in the registry:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]  
>  DisableScandiskOnBoot=01

 More Info [MS KB152404](http://support.microsoft.com/kb/152404 "ScanDisk Runs After Improper Shutdown or Hard Disk Error [Q152404]")  
  
 Credits [regedit.com](http://www.regedit.com/)