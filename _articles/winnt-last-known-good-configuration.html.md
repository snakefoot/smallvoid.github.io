---
title: 'Using Last Known Good Configuration'
date: '2004-06-10T01:58:25+02:00'
permalink: /article/winnt-last-known-good-configuration.html
author: Snakefoot
excerpt: 'The Last Known Good Configuration makes it possible to rollback to the previous good state of the system registry hive.'
type: post
id: 257
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags:
    - last-known-good-configuration
    - system-recovery
---
There is performed a backup of the system configuration, after each successful login. This name of this backup is Last Known Good Configuration (LKGC). It is possible to make use of the LKGC during the startup of Windows (Press F8). This enables one to recover from different situations where Windows cannot boot:

- Installed faulty driver
- Disabled critical driver
- Disabled critical service
 
 The LKGC resides in the following registry file (Along with the active configuration):
> %systemroot%\\System32\\Config\\System  
>   
>  Note if this file becomes corrupted, then it means that both the active configuration and LKGC becomes corrupted.

 The LKGC can be seen using the registry editor:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\ControlSetXXX\] (Ex. ControlSet002)  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\Select\]  
>  LastKnownGood = XXX  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20100010%20Q100010" rel="nofollow" title="What are Control Sets? What is CurrentControlSet? [Q100010]">MS KB100010</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20142033%20Q142033" rel="nofollow" title="Restoring Previous ControlSet After Using LastKnownGood [Q142033]">MS KB142033</a>

 Note it is possible to configure whether the LKGC should be created after every login:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ReportBootOk = 1 (Enabled = 1, Disabled = 0, Default = No Value; Enabled)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20136441%20Q136441" rel="nofollow" title="Last Known Good Always Restores Original Boot Settings [Q136441]">MS KB136441</a>

 Note to make best use of LKGC, then after making a "critical" change and restarted, then don't login right away (Or [Automatic Login](/article/winnt-automatic-logon.html)). Instead wait about a minute after the login screen has shown itself, so that services etc. can load completely and if no errors occurs then login.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20101790%20Q101790" rel="nofollow" title="Information on Last Known Good Control Set [Q101790]">MS KB101790</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20307852%20Q307852" rel="nofollow" title="How to start your computer by using the Last Known Good Configuration feature in Windows XP [Q307852]">MS KB307852</a>  