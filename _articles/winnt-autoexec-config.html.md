---
title: 'MSDOS subsystem and Autoexec.nt / Config.nt'
date: '2001-01-01T13:09:07+01:00'
permalink: /article/winnt-autoexec-config.html
author: Snakefoot
excerpt: 'How to configure the MS-DOS subsystem using Autoexec.nt and Config.nt.'
type: post
id: 23
categories:
    - windows-nt4_command-prompt
    - windows-xp_command-prompt
    - windows-2000_command-prompt
    - windows-2003_command-prompt
tags:
    - dos-emulator
    - subsystem
---
CONFIG.SYS and AUTOEXEC.BAT are files essential to DOS. They also exist in Windows NT but they are called CONFIG.NT and AUTOEXEC.NT and reside in C:\\WINNT\\SYSTEM32.  
  
 They are executed every time a DOS subsystem is created within NTVDM.EXE, which means every time you start a 16-bit program (Like Command.com). They will configure the environment in which the program will be executed in. This includes WinNT DOS drivers like ANSI.SYS.  
  
 Note if the AUTOEXEC.NT has been damaged/lost (usually deleted by a virus, so remember to update virus scanner), then one can usually restore the AUTOEXEC.NT by copying it from \\Windows\\Repair to \\Windows\\System32. When running a DOS program without the AUTOEXEC.NT being in place it will give the following error message:

> *16 bit Windows Subsystem - C:\\Windows\\System32\\AUTOEXEC.NT. The system file is not suitable for running MS-DOS and Microsoft Windows applications. Choose 'Close' to terminate the application.*  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20324767%20Q324767" rel="nofollow" title="Error message when you install or start an MS-DOS or 16-bit Windows-based program [Q324767]">MS KB324767</a>

 Note it possible for Windows NT4/2000 to parse the AUTOEXEC.BAT (Placed in the root of the system-drive) during user logon, and append the PATH [environment variable](/article/winnt-environment-variables.html) to the user PATH. The parsing of the AUTOEXEC.BAT is controlled by this STRING registry value:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ParseAutoexec = "0" (Default = "1", Ignore = "0")  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20124551%20Q124551" rel="nofollow" title="INFO: Configuring Parsing of the AUTOEXEC.BAT File [Q124551]">MS KB124551</a>

 More Info <a href="https://www.bing.com/search?q=KB%20101875%20Q101875" rel="nofollow" title="How to Enable ANSI.SYS in a Command Window [Q101875]">MS KB101875</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20103656%20Q103656" rel="nofollow" title="Troubleshooting 16-Bit Windows Applications [Q103656]">MS KB103656</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20129128%20Q129128" rel="nofollow" title="SUBST Command Does Not Execute in AUTOEXEC.NT [Q129128]">MS KB129128</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20165214%20Q165214" rel="nofollow" title="Troubleshooting MS-DOS-Based Programs in Windows [Q165214]">MS KB165214</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20220155%20Q220155" rel="nofollow" title="Troubleshooting NTVDM and WOW Startup Errors [Q220155]">MS KB220155</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20301911%20Q301911" rel="nofollow" title="How to use the Program Compatibility Wizard in Windows XP [Q301911]">MS KB301911</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20314106%20Q314106" rel="nofollow" title="Troubleshooting MS-DOS-based programs in Windows XP [Q314106]">MS KB314106</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20314495%20Q314495" rel="nofollow" title="How to Troubleshoot 16-Bit Windows Programs in Windows XP [Q314495]">MS KB314495</a>  
  
 Related [Lock MSDOS subsystem to a single core to avoid crashes](/article/winnt-process-affinity.html)  
 Related [Disable the MSDOS and Win16 subsystem](/article/winnt-ntvdm-subsystem.html)  