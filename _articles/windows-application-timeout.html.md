---
title: 'Configure timeout for application termination'
date: '2000-01-01T01:22:42+01:00'
permalink: /article/windows-application-timeout.html
author: Snakefoot
excerpt: 'Change when an application is considered as deadlocked and should be terminated.'
type: post
id: 278
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-95_troubleshoot
    - windows-98_troubleshoot
    - windows-me_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags: []
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
  
 More Info <a href="https://www.bing.com/search?q=KB%20123058%20Q123058" rel="nofollow" title="Closing Timed-Out Applications Without Choosing End Task [Q123058]">MS KB123058</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20305788%20Q305788" rel="nofollow" title="HOW TO: Increase Shutdown Time So That Processes Can Quit Properly in Windows XP [Q305788]">MS KB305788</a>  
  
 Credits [www.mdgx.com](http://www.mdgx.com/)