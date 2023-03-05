---
title: 'Restrict users from replacing a system DLL'
date: '2002-02-03T21:35:06+01:00'
status: publish
permalink: /article/winnt-secure-system-dll.html
author: Snakefoot
excerpt: 'Protect against DLL injections to avoid performing malicous code.'
type: post
id: 453
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - code-injection
post_format: []
tags:
    - code-injection
---
If a malicious user can interactively log on your computer. Then the user can load a DLL with the same name as a core operating system DLL and change the KnownDLLs list to point to this DLL. This will cause the operating system to perform the malicious DLL code in administrator mode, enabling the malicious user to get admin rights.  
  
 To avoid this one should update this DWORD registry entry:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  ProtectionMode=1 (Disabled = 0, Enabled = 1)  
>   
>  Note WinNT4 need to have SP5 installed before this registry entry works.  
>   
>  More Info [MS KB218473](http://support.microsoft.com/kb/218473 "Restricting Changes to Base System Objects [Q218473]")  
>  More Info [MS KB222159](http://support.microsoft.com/kb/222159 "Symbolic Link Case Sensitivity Exploit Bypasses System Security [Q222159]")  
>  More Info [MS KB244995](http://support.microsoft.com/kb/244995 "Base System Object Restrictions Are Not Enabled by Default [Q244995]")  
>  More Info [MS KB253821](http://support.microsoft.com/kb/253821 "System Error 85 with "NET USE" Command [Q253821]")

 There is a search order which is used when an application requests a DLL.
1. Look in the application folder
2. Look in the current working folder (Dangerous)
3. Look in the system folder
4. Search through the [system PATH](/article/executing-program-path.html)
 
 If a malicious user can inject a DLL in a folder, which an application will use as current working folder, and that application loads a system DLL. Then the application will load the injected DLL instead of the proper system DLL. It is possible to change the search order so it looks in the system-folder right after looking in the application folder:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Session Manager\]  
>  SafeDllSearchMode = 1 (Win2k/WinXP Default = 0, WinXP SP1/Win2k3 Default = 1)  
>   
>  Note Win2k need to have SP3 installed before this registry entry works.  
>   
>  More Info [MS KB306850](http://support.microsoft.com/kb/306850 "Programs Start Slowly or Slow Logon if the Network Connection to Your Home Folder Is Slow [Q306850]")

 Note when launching an application using **Run...** from the Start-menu, then it will also use the search order above to find the application executable. But it applies an extra step before searching through the system PATH, which is to look in the user home folder. Make it ignore the home-path by setting this DWORD registry key:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  StartRunNoHOMEPATH = 1 (Default - 0)  
>   
>  More Info [MS KB264061](http://support.microsoft.com/kb/264061 "Home Folder Is Searched First When You Try to Run a Program [Q264061]")

 Instead of ignoring the homepath, then one can configure it to first search the system path, and then look in the home-path:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  SafeProcessSearchMode = 1 (Default = 0)  
>   
>  More Info [MS KB905890](http://support.microsoft.com/kb/905890 "A program may run very slowly if the network connection to your home folder is slow")

 Credits [jsifaq.com](http://www.jsifaq.com/)