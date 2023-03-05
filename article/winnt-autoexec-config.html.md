---
title: 'MSDOS subsystem and Autoexec.nt / Config.nt'
date: '2001-01-01T13:09:07+01:00'
status: publish
permalink: /article/winnt-autoexec-config.html
author: Snakefoot
excerpt: 'How to configure the MS-DOS subsystem using Autoexec.nt and Config.nt.'
type: post
id: 23
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - dos-emulator
    - subsystem
post_format: []
tags:
    - 'subsystem,dos-emulator'
---
CONFIG.SYS and AUTOEXEC.BAT are files essential to DOS. They also exist in Windows NT but they are called CONFIG.NT and AUTOEXEC.NT and reside in C:\\WINNT\\SYSTEM32.  
  
 They are executed every time a DOS subsystem is created within NTVDM.EXE, which means every time you start a 16-bit program (Like Command.com). They will configure the environment in which the program will be executed in. This includes WinNT DOS drivers like ANSI.SYS.  
  
 Note if the AUTOEXEC.NT has been damaged/lost (usually deleted by a virus, so remember to update virus scanner), then one can usually restore the AUTOEXEC.NT by copying it from \\Windows\\Repair to \\Windows\\System32. When running a DOS program without the AUTOEXEC.NT being in place it will give the following error message:

> *16 bit Windows Subsystem - C:\\Windows\\System32\\AUTOEXEC.NT. The system file is not suitable for running MS-DOS and Microsoft Windows applications. Choose 'Close' to terminate the application.*  
>   
>  More Info [MS KB324767](http://support.microsoft.com/kb/324767 "Error message when you install or start an MS-DOS or 16-bit Windows-based program [Q324767]")

 Note it possible for Windows NT4/2000 to parse the AUTOEXEC.BAT (Placed in the root of the system-drive) during user logon, and append the PATH [environment variable](/article/winnt-environment-variables.html) to the user PATH. The parsing of the AUTOEXEC.BAT is controlled by this STRING registry value:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ParseAutoexec = "0" (Default = "1", Ignore = "0")  
>   
>  More Info [MS KB124551](http://support.microsoft.com/kb/124551 "INFO: Configuring Parsing of the AUTOEXEC.BAT File [Q124551]")

 More Info [MS KB101875](http://support.microsoft.com/kb/101875 "How to Enable ANSI.SYS in a Command Window [Q101875]")  
 More Info [MS KB103656](http://support.microsoft.com/kb/103656 "Troubleshooting 16-Bit Windows Applications [Q103656]")  
 More Info [MS KB129128](http://support.microsoft.com/kb/129128 "SUBST Command Does Not Execute in AUTOEXEC.NT [Q129128]")  
 More Info [MS KB165214](http://support.microsoft.com/kb/165214 "Troubleshooting MS-DOS-Based Programs in Windows [Q165214]")  
 More Info [MS KB220155](http://support.microsoft.com/kb/220155 "Troubleshooting NTVDM and WOW Startup Errors [Q220155]")  
 More Info [MS KB301911](http://support.microsoft.com/kb/301911 "How to use the Program Compatibility Wizard in Windows XP [Q301911]")  
 More Info [MS KB314106](http://support.microsoft.com/kb/314106 "Troubleshooting MS-DOS-based programs in Windows XP [Q314106]")  
 More Info [MS KB314495](http://support.microsoft.com/kb/314495 "How to Troubleshoot 16-Bit Windows Programs in Windows XP [Q314495]")  
  
 Related [Lock MSDOS subsystem to a single core to avoid crashes](/article/winnt-process-affinity.html)  
 Related [Disable the MSDOS and Win16 subsystem](/article/winnt-ntvdm-subsystem.html)  