---
title: 'Restrict users from replacing a system DLL'
date: '2002-02-03T21:35:06+01:00'
permalink: /article/winnt-secure-system-dll.html
author: Snakefoot
excerpt: 'Protect against DLL injections to avoid performing malicous code.'
type: post
id: 453
categories:
    - windows-2003_user-security
    - windows-nt4_user-security
    - windows-xp_user-security
    - windows-2000_user-security
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
>  More Info <a href="https://www.bing.com/search?q=KB%20218473%20Q218473" rel="nofollow" title="Restricting Changes to Base System Objects [Q218473]">MS KB218473</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20222159%20Q222159" rel="nofollow" title="Symbolic Link Case Sensitivity Exploit Bypasses System Security [Q222159]">MS KB222159</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20244995%20Q244995" rel="nofollow" title="Base System Object Restrictions Are Not Enabled by Default [Q244995]">MS KB244995</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20253821%20Q253821" rel="nofollow" title="System Error 85 with 'NET USE' Command [Q253821]">MS KB253821</a>

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
>  More Info <a href="https://www.bing.com/search?q=KB%20306850%20Q306850" rel="nofollow" title="Programs Start Slowly or Slow Logon if the Network Connection to Your Home Folder Is Slow [Q306850]">MS KB306850</a>

 Note when launching an application using **Run...** from the Start-menu, then it will also use the search order above to find the application executable. But it applies an extra step before searching through the system PATH, which is to look in the user home folder. Make it ignore the home-path by setting this DWORD registry key:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  StartRunNoHOMEPATH = 1 (Default - 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20264061%20Q264061" rel="nofollow" title="Home Folder Is Searched First When You Try to Run a Program [Q264061]">MS KB264061</a>

 Instead of ignoring the homepath, then one can configure it to first search the system path, and then look in the home-path:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\]  
>  SafeProcessSearchMode = 1 (Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20905890%20Q905890" rel="nofollow" title="A program may run very slowly if the network connection to your home folder is slow">MS KB905890</a>

 Credits [jsifaq.com](http://www.jsifaq.com/)