---
title: 'Restrict access to the OS/2 and POSIX subsystem'
date: '2000-01-01T22:05:59+01:00'
permalink: /article/winnt-subsystem.html
author: Snakefoot
excerpt: 'Disable legacy subsystems to prevent attackers from using these subsystems as base of attack.'
type: post
id: 371
categories:
    - windows-nt4_user-security
    - windows-2000_user-security
tags:
    - os2
    - posix
    - subsystem
---
Windows NT has support for several subsystems, the most common ones are DOS and 16 Bit Windows. It also has support for OS/2 1.0(No GUI), and it is regarded as a security issue to have the OS/2 and POSIX support enabled. Before disabling OS/2 support make sure that you are not using OS/2 dependent legacy applications or cross-platform executables with OS/2 support (Like HIEW).

##### Disable OS/2 and POSIX subsystem

1. Start the registry editor and remove the following entries: 
  - \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\**OS/2 Subsystem for NT**\]
  - \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Environment\]  
      **Os2LibPath=**
  - \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\SubSystems\]  
      **Optional=**  
      **OS2=**  
      **Posix=**
2. Enter the %Windir%\\System32\\Dllcache directory and remove these files (Because of [Windows File Protection](/article/winnt-wfp.html))  
  
  - os2.exe
  - os2ss.exe
  - os2srv.exe
3. Enter the %Windir%\\System32 directory and rename/remove these files: 
  - os2.exe
  - os2ss.exe
  - os2srv.exe
  - psxss.exe
  - posix.exe
  - psxdll.dll
4. Enter the %Windir%\\System32\\OS2 directory and rename/remove these files: 
  - All files except the DLL folder and its contents
 
 More Info <a href="https://www.bing.com/search?q=KB%20101270%20Q101270" rel="nofollow" title="Disabling the POSIX Subsystem [Q101270]">MS KB101270</a>  
  
 Note that with Windows XP the OS2 and POSIX subsystem is not installed, though the registry entries are still created. More Info <a href="https://www.bing.com/search?q=KB%20308259%20Q308259" rel="nofollow" title="OS/2 and POSIX Are Not Supported in Windows XP [Q308259]">MS KB308259</a>  
  
 Credits [NSA Win2k Security Guide](http://csrc.nist.gov/itsec/guidance_W2Kpro.html)  
 Credits [NSA WinXP Security Guide](http://csrc.nist.gov/itsec/guidance_WinXP.html)  