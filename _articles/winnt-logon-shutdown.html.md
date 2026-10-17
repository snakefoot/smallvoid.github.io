---
title: 'Allow users to shutdown the machine without login'
date: '2000-01-01T22:25:11+01:00'
permalink: /article/winnt-logon-shutdown.html
author: Snakefoot
excerpt: 'Extend the login dialog with the option to shutdown the computer without having given credentials.'
type: post
id: 457
categories:
    - windows-2003_user-security
    - windows-nt4_user-security
    - windows-xp_user-security
    - windows-2000_user-security
tags:
    - windows-login
---
The login box includes a shutdown button, that can hidden/shown dependent on whether one wants unauthorized users to shutdown your mission critical server, or you don't bother to login to restart the computer.  
  
 To enable/disable the shutdown button in Windows NT4:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  ShutdownWithoutLogon=1  
>   
>  More info <a href="https://www.bing.com/search?q=KB%20114817%20Q114817" rel="nofollow" title="No Shutdown Button in Windows NT Server Welcome Screen [Q114817]">MS KB114817</a>  
>  More info <a href="https://www.bing.com/search?q=KB%20216083%20Q216083" rel="nofollow" title="How to Disable the Shut Down Button on the Logon Information Window [Q216083]">MS KB216083</a>

 To enable/disable the shutdown button in Windows 2000:
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to **Local Policies** -&gt; **Security Options**
3. Change the option **Allow system to be shutdown without having to logon**
 
 More info <a href="https://www.bing.com/search?q=KB%20232399%20Q232399" rel="nofollow" title="How to Enable Logon Screen Shutdown Button in Windows 2000 Server [Q232399]">MS KB232399</a>  
 More info <a href="https://www.bing.com/search?q=KB%20313924%20Q313924" rel="nofollow" title="How To Make the Shutdown Button Unavailable in the Logon Dialog Box in Windows 2000 [Q313924]">MS KB313924</a>  
  
 To enable/disable the shutdown button in Windows XP/2003 (Also affects [Welcome Screen](/article/winxp-welcome-screen.html)):
1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to **Local Policies** -&gt; **Security Options**
3. Change the option **Shutdown: Allow system to be shut down without having to log on**
 
 More info <a href="https://www.bing.com/search?q=KB%20816569%20Q816569" rel="nofollow" title="HOW TO: Make the Shutdown Button Unavailable in the Logon Dialog Box in Windows Server 2003 [Q816569]">MS KB816569</a>  