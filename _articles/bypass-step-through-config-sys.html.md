---
title: 'Bypass or step through Config.sys and Autoexec.bat'
date: '2000-01-01T00:38:20+01:00'
permalink: /article/bypass-step-through-config-sys.html
author: Snakefoot
excerpt: 'How to bypass or single step through the startup files Config.sys and Autoexec.bat using the keyboard keys F5 and F8.'
type: post
id: 58
categories:
    - ms-dos_tips
tags:
    - autoexec-bat
    - config-sys
    - system-recovery
---
MS DOS 6.0 introduced the ability to bypass the Config.sys and Autoexec.bat, and only load the Himem.sys, or single step through the Config.sys and Autoexec.bat. This can be useful if having problems with diagnosing what device driver or other terminate and stay resident (TSR) that is causing problems.  
  
 These options can be activated by pressing the keyboard key **F8** during startup, when it displays "Starting MS-DOS ..." (Shown for two seconds). If pressing **F5** instead of F8 then it will bypass the startup files without showing any options. MS DOS 7.1 (Win98) also reacts to **CTRL** being held down (same as F8), instead of waiting for the right moment to press F5 or F8.  
  
 Note it is possible to remove the 2 seconds delay (ex. if using [Multiple configurations](/article/dos-multiple-configurations.html)), by adding the following switch to Config.sys:

> switches=/f

 Note it is possible to disable the F5 and F8 entirely by adding the following switch to Config.sys:

> switches=/n

 More Info <a href="https://www.bing.com/search?q=KB%2093602%20Q93602" rel="nofollow" title="How to Disable F5 and F8 During Startup in MS-DOS [Q93602]">MS KB93602</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2096332%20Q96332" rel="nofollow" title="F5 and F8 Keys Do Not Seem to Affect Startup Files [Q96332]">MS KB96332</a>  