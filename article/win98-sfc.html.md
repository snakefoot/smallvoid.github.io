---
title: 'Using the System File Checker in Windows 98'
date: '2003-01-10T01:22:21+01:00'
status: publish
permalink: /article/win98-sfc.html
author: Snakefoot
excerpt: 'System File Checker is able to verify that system files are intact.'
type: post
id: 179
category:
    - Troubleshoot
tag:
    - system-file-checker
post_format: []
tags:
    - system-file-checker
---
With Windows 95 Microsoft learned that much of the instability of Windows was caused by 3rd party applications overwriting Windows system files and causing havoc. To counter this Microsoft released the System File Checker(SFC) in Windows 98. With this utility one can scan all Windows System Files and restore altered files.  
  
[How to scan for altered files or restore a single file](http://www.microsoft.com/windows98/usingwindows/maintaining/tips/beginner/sysfilecheck.asp) using SFC.EXE  
  
 Note that one can set the SFC to point to a different directory to restore files from. This can be useful in case one have upgraded to a newer version of the Internet Explorer, where one should point SFC to the install files of the newer version. If restoring Internet Explorer related files from the original CAB-files will lead to mixed binaries with unpredictable results to follow.  
  
 Note that [Windows Me uses System File Protection](/article/winme-system-restore.html) and doesn't have a System File Checker.  
  
 More Info [MS KB185836](http://support.microsoft.com/kb/185836 "Description of the System File Checker Tool (Sfc.exe) [Q185836]")  
 More Info [MS KB188186](http://support.microsoft.com/kb/188186 "How the System File Checker Baseline Is Determined [Q188186]")  
 More Info [MS KB192832](http://support.microsoft.com/kb/192832 "System File Checker Tool Extracts Incorrect File Versions [Q192832]")