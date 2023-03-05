---
title: 'Allow users to shutdown the machine without login'
date: '2000-01-01T22:25:11+01:00'
status: publish
permalink: /article/winnt-logon-shutdown.html
author: Snakefoot
excerpt: 'Extend the login dialog with the option to shutdown the computer without having given credentials.'
type: post
id: 457
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - windows-login
post_format: []
tags:
    - windows-login
---
The login box includes a shutdown button, that can hidden/shown dependent on whether one wants unauthorized users to shutdown your mission critical server, or you don't bother to login to restart the computer.  
  
 To enable/disable the shutdown button in Windows NT4:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ShutdownWithoutLogon=1  
>   
>  More info [MS KB114817](http://support.microsoft.com/kb/114817 "No Shutdown Button in Windows NT Server Welcome Screen [Q114817]")  
>  More info [MS KB216083](http://support.microsoft.com/kb/216083 "How to Disable the Shut Down Button on the Logon Information Window [Q216083]")

 To enable/disable the shutdown button in Windows 2000:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to **Local Policies** -&gt; **Security Options**
3. Change the option **Allow system to be shutdown without having to logon**
 
 More info [MS KB232399](http://support.microsoft.com/kb/232399 "How to Enable Logon Screen Shutdown Button in Windows 2000 Server [Q232399]")  
 More info [MS KB313924](http://support.microsoft.com/kb/313924 "How To Make the Shutdown Button Unavailable in the Logon Dialog Box in Windows 2000 [Q313924]")  
  
 To enable/disable the shutdown button in Windows XP/2003 (Also affects [Welcome Screen](/article/winxp-welcome-screen.html)):
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to **Local Policies** -&gt; **Security Options**
3. Change the option **Shutdown: Allow system to be shut down without having to log on**
 
 More info [MS KB816569](http://support.microsoft.com/kb/816569 "HOW TO: Make the Shutdown Button Unavailable in the Logon Dialog Box in Windows Server 2003 [Q816569]")  