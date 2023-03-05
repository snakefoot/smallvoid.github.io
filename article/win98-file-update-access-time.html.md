---
title: 'Disable the automatic updating of file access time'
date: '2001-02-07T23:33:44+01:00'
status: publish
permalink: /article/win98-file-update-access-time.html
author: Snakefoot
excerpt: 'Lower the disk activity by disabling the updating of when a file was last accessed.'
type: post
id: 100
category:
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-access-time
    - file-system
post_format: []
tags:
    - 'file-access-time,disk-performance'
---
When a file is opened then the last access timestamp for the file is updated. This timestamp can be useful for applications that detects, whether certain files have been used recently. If not using such applications, then one might consider disabling the updating of this timestamp, to make file operations quicker.  
  
 To disable the updating of the file access time add this line in your CONFIG.SYS

> ACCDATE = C- D- E- F- G-

 If you don't have that many drives just remove the drive letters, or add them if the other way. Drive letter A: is disabled by default.  
  
 You can find this tip in your CONFIG.TXT in the WINDOWS directory [MS Info](http://support.microsoft.com/support/windows/readme/Win98se/W98seconfigtxt.asp#ACCDATE "Windows 98 Second Edition Config.txt File")  
  
 Doesn't work for Win95 [MS KB182465](http://support.microsoft.com/kb/182465 "ACCDATE Command Line Does Not Work with Windows 95 [Q182465]")  
  
 Doesn't work for WinMe [MS KB274646](http://support.microsoft.com/kb/274646 "Understanding the Settings in the Windows Millennium Edition Config.sys File [Q274646]")  