---
title: 'Quick shutdown in Windows 98'
date: '2003-02-22T19:40:22+01:00'
status: publish
permalink: /article/win98-fast-reboot.html
author: Snakefoot
excerpt: 'How to configure the fast shutdown feature in Windows 98.'
type: post
id: 106
category:
    - Tips
tag:
    - reboot
    - restart
    - shutdown
post_format: []
tags:
    - 'reboot,restart,shutdown'
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
  
 More Info [MS KB145926](http://support.microsoft.com/kb/145926 "How to Troubleshoot Windows 95 Shutdown Problems [Q145926]")  
 More Info [MS KB186925](http://support.microsoft.com/kb/186925 "Restarting Computer While Holding Down SHIFT Key Hangs Windows [Q186925]")  
 More Info [MS KB196008](http://support.microsoft.com/kb/196008 "Computer Stops Responding When You Try to Shut It Down [Q196008]")  
 More Info [MS KB202633](http://support.microsoft.com/kb/202633 "How to Troubleshoot Windows 98 Shutdown Problems [Q202633]")  
 More Info [MS KB238096](http://support.microsoft.com/kb/238096 "Problems Shutting Down Windows 98 Second Edition [Q238096]")  
 More Info [MS KB273746](http://support.microsoft.com/kb/273746 "How to Troubleshoot Windows Me Shutdown Problems [Q273746]")  
  
 Credits [aumha.org](http://aumha.org/win4/a/shutdown.htm)