---
title: 'Configure timeout for application termination'
date: '2000-01-01T01:22:42+01:00'
status: publish
permalink: /article/windows-application-timeout.html
author: Snakefoot
excerpt: 'Change when an application is considered as deadlocked and should be terminated.'
type: post
id: 278
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
---
It is possible to control how quickly windows automatically should end applications.  
  
 Windows can detect when an applications freezes if it don't respond within a specific time, then prompt user:

> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  HungAppTimeout = "2500" (Default = 5000, Min = 1, Max = 65536)

 Windows can be told to automatically close freezed applications without asking user first:  
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  AutoEndTasks = "1" (Default = 0, Enable = 1, Disable = 0)

 Windows can force close applications at shutdown which don't close within a specific time :  
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  WaitToKillAppTimeout = "10000" (Default = 20000, Min = 1, Max = 65536)

 Note if lowering the timeout values too much, then it might lead to improper shutdown of the applications, which might lead to half-written/ invalid / faulty data that will keep the application from starting properly again.  
  
 More Info [MS KB123058](http://support.microsoft.com/kb/123058 "Closing Timed-Out Applications Without Choosing End Task [Q123058]")  
 More Info [MS KB305788](http://support.microsoft.com/kb/305788 "HOW TO: Increase Shutdown Time So That Processes Can Quit Properly in Windows XP [Q305788]")  
  
 Credits [www.mdgx.com](http://www.mdgx.com/)