---
title: 'Quick shutdown in Windows 98'
date: '2003-02-22T19:40:22+01:00'
permalink: /article/win98-fast-reboot.html
author: Snakefoot
excerpt: 'How to configure the fast shutdown feature in Windows 98.'
type: post
id: 106
categories:
    - windows-98_tips
tags:
    - reboot
    - restart
    - shutdown
---
With Windows 98 a new feature came which makes the shutdown/restart quicker.

- Start the System Configuration Utility (msconfig.exe)
- Press the "Advanced"-button on the "General"-tab
- Check/Uncheck "Disable fast shutdown"
 
 This option reflects the this registry key:
 
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Shutdown\]  
 >  FastReboot = "0" ("1" = Enabled, "0" = Disabled)

 Note many people experience shutdown and restart problems when enabling fast reboot, so if enabling this option test that the computer still is able to restart and shutdown properly.  
  
 Note this option becomes disabled by installing the Shutdown patch.  
  
 More Info <a href="https://www.bing.com/search?q=KB+145926+Q145926" rel="nofollow" title="How to Troubleshoot Windows 95 Shutdown Problems [Q145926]">MS KB145926</a>  
 More Info <a href="https://www.bing.com/search?q=KB+186925+Q186925" rel="nofollow" title="Restarting Computer While Holding Down SHIFT Key Hangs Windows [Q186925]">MS KB186925</a>  
 More Info <a href="https://www.bing.com/search?q=KB+196008+Q196008" rel="nofollow" title="Computer Stops Responding When You Try to Shut It Down [Q196008]">MS KB196008</a>  
 More Info <a href="https://www.bing.com/search?q=KB+202633+Q202633" rel="nofollow" title="How to Troubleshoot Windows 98 Shutdown Problems [Q202633]">MS KB202633</a>  
 More Info <a href="https://www.bing.com/search?q=KB+238096+Q238096" rel="nofollow" title="Problems Shutting Down Windows 98 Second Edition [Q238096]">MS KB238096</a>  
 More Info <a href="https://www.bing.com/search?q=KB+273746+Q273746" rel="nofollow" title="How to Troubleshoot Windows Me Shutdown Problems [Q273746]">MS KB273746</a>  
  
 Credits [aumha.org](http://aumha.org/win4/a/shutdown.htm)