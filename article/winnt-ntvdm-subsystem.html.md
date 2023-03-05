---
title: 'Disable the MSDOS and Win16 subsystem'
date: '2010-01-21T01:32:25+01:00'
status: publish
permalink: /article/winnt-ntvdm-subsystem.html
author: Snakefoot
excerpt: 'For security measures then one should consider disabling the ability to launch the 16 bit subsystem.'
type: post
id: 825
category:
    - Tips
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - dos-emulator
    - subsystem
post_format: []
tags:
    - 'subsystem,dos-emulator'
---
A great advantage of Microsoft Windows is that old software usually continue to work even if upgrading to the next version of Microsoft Windows.  
  
 All 32 bit versions of Microsoft Windows includes a [16 bit emulator subsystem](/article/winnt-autoexec-config.html), which allows one to run standard DOS and Win16 application like one could in [Windows 3.1](http://en.wikipedia.org/wiki/Windows_3.1x). **64 bit versions of Windows no longer includes the 16 bit emulator subsystem.**

> Microsoft Windows also once included a [OS/2 and a POSIX emulator](/article/winnt-subsystem.html), but they were removed with Windows XP/2003. More Info [MS KB308259](http://support.microsoft.com/kb/308259 "POSIX and OS/2 are not supported in Windows XP or in Windows Server 2003 [Q308259]")

 Many regards these subsystems as possible security holes, and prefere to disable them to avoid any surprises. On Windows XP / 2003 and newer the ntvdm.exe can be stopped from running with this Group Policy:
> Computer Configuration\\Administrative Templates\\Windows Components\\Application Compatibility  
>  Prevent access to 16-bit applications  
>   
>  HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\AppCompat\]  
>  VDMDisallowed = 0

 If running Windows NT/2000 (or want to ensure no one starts ntvdm.exe), then one can change the [NTFS permissions to the file](/article/ntfs-access-control.html), so it no longer can be executed.  
  
 If just want to disable the ability to run MSDOS and Win16 applications without disabling the subsystem, then one can modify the following registry key (To WOW2):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\**WOW**\]  
>  CmdLine = "..."  
>  WowCmdLine = "..."  
>   
>  More Info [MS KB220159](http://support.microsoft.com/kb/220159 "Disabling the MSDOS and WOWEXEC Subsystems on Terminal Server")

 Note if disabling the DOS subsystem then any batch scripts with the .BAT file extension, should be renamed to use the .CMD file extension.  
  
 More Info [SecurityFocus.com](http://www.securityfocus.com/bid/37864/info "CVE-2010-0232") (Exploit sample code)