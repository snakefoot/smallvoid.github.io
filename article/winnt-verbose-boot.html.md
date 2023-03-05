---
title: 'Verbose status messages during boot, logon, logoff and shutdown'
date: '2001-02-06T20:07:11+01:00'
status: publish
permalink: /article/winnt-verbose-boot.html
author: Snakefoot
excerpt: 'Extend the level of informational messages during Windows startup and shutdown.'
type: post
id: 385
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - windows-login
post_format: []
tags:
    - windows-login
---
Increase the level of status message being shown during startup and shutdown to a more clear picture of what is happening.  
  
 Change to verbose with this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
>  VerboseStatus=1

 This setting can also be configured through the [Group Policy Editor](/article/winnt-group-policy-registry.html):
 - **Windows 2003/XP/2000** - Computer Configuration -&gt; Administrative Tools -&gt; System and change the option "Verbose vs. normal status messages".
 - **Windows Vista/2008** - Computer Configuration -&gt; Administrative Templates -&gt; System and change the option "Verbose vs normal status messages"
 
 If the following DWORD registry entry is set to 1 then no messages is shown at all:
 > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
 >  DisableStatusMessages = 0 (0 = Show messages, 1 = Hide messages)

 More Info [MS KB316243](http://support.microsoft.com/kb/316243 "HOW TO: Receive Verbose Startup, Shutdown, Logon, and Logoff Status Messages [Q316243]")  
 More Info [MS KB325376](http://support.microsoft.com/kb/325376 "How To Enable Verbose Startup, Shutdown, Logon, and Logoff Status Messages in the Windows Server 2003 Family [Q325376]")  
  
 Credits [is-it-true.org](http://www.is-it-true.org/)