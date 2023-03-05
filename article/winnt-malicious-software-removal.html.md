---
title: 'Microsoft Malicious Software Removal Tool'
date: '2005-11-14T18:32:18+01:00'
status: publish
permalink: /article/winnt-malicious-software-removal.html
author: Snakefoot
excerpt: 'Security utility for checking if computer is infected with malware, and if so remove it.'
type: post
id: 518
category:
    - Utilities
    - Utilities
tag:
    - virus
post_format: []
tags:
    - virus
---
The [Malicious Software Removal Tool](http://www.microsoft.com/downloads/details.aspx?FamilyId=AD724AE0-E72D-4F54-9AB3-75B8EB148356) (MRT) scans for [popular infections](http://support.microsoft.com/kb/890830 "The Microsoft Windows Malicious Software Removal Tool helps remove specific, prevalent malicious software from computers that are running supported versions of Windows [Q890830]") and if any detected then they are removed. It is a run-once tool, so it doesn't reside in memory and monitor the system like [MS Windows Defender](http://www.microsoft.com/athome/security/spyware/).  
  
 The tool is updated every month and if using [Automatic Update](/article/winnt-services-wuauserv.html), then it will automatically download the update and scan the computer every month.  
  
 When running %windir%\\System32\\Mrt.exe a log is created (%windir%\\Debug\\Mrt.log), where actions and [errors](http://support.microsoft.com/kb/891717 "How to troubleshoot an error when you run the Microsoft Windows Malicious Software Removal Tool [Q891717]") can be seen.