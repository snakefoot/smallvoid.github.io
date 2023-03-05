---
title: 'Debugging Tools'
date: '2006-02-25T20:49:07+01:00'
status: publish
permalink: /article/winnt-windbg.html
author: Snakefoot
excerpt: 'Microsoft Windbg makes it possible to diagnose what caused a BSOD, so one can replace the device that caused it.'
type: post
id: 270
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - blue-screen-of-death
    - debugging-tools
    - memory-dump
    - windbg
post_format: []
tags:
    - 'windbg,debugging-tools,memory-dump,blue-screen-of-death'
---
[Microsoft Debugging Tools](http://www.microsoft.com/whdc/DevTools/Debugging/default.mspx) can be used for tracking down the cause of a Blue Screen of Death (BSOD). Windows NT treats installed drivers as trusted code, so if having installed a poorly written driver, then it might cause Windows NT to crash with a BSOD. When Windows NT crashes it also attempts to create a [memory dump](http://support.microsoft.com/kb/254649 "Overview of memory dump file options for Windows 2000, Windows XP, Windows Server 2003, Windows Vista, Windows Server 2008, Windows 7, and Windows Server 2008 R2 [Q254649]"), which can be used for tracking down the cause of the BSOD.  
1. Start WinDbg and in the File-menu select "Open Crash Dump..."
2. Point it to the memory dump created during the BSOD and press Ok
3. It will open a Command window and begin to read the memory dump
4. When it is done look for the following line, and you will find the filename of the driver:
   > **Probably caused by :**  ....
5. Use your favorite search engine to find out what device uses the driver, or do a file search on your computer for the filename and view the file properties.
 
 More Info [MS KB307973](http://support.microsoft.com/kb/307973 "How to configure system failure and recovery options in Windows [Q307973]")  
 More Info [MS KB315263](http://support.microsoft.com/kb/315263 "How to read the small memory dump files that Windows creates for debugging [Q315263]")  