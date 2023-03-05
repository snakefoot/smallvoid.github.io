---
title: 'Configure a secure network login to a domain'
date: '2003-09-08T21:37:57+02:00'
status: publish
permalink: /article/win9x-domain-login.html
author: Snakefoot
excerpt: 'Forcing the user to provide credentials before being allowed to use Windows 9x.'
type: post
id: 215
category:
    - Network
    - Network
    - Network
tag:
    - user-account
    - windows-domain
    - windows-login
post_format: []
tags:
    - 'user-account,windows-login,windows-domain'
---
Clear the username of the previous logged on user, so it is not displayed to the next user (Will disable [Automatic Login](/article/win9x-automatic-login.html)):

> \[HKEY\_LOCAL\_MACHINE \\Network \\Logon\]  
>  DontShowLastUser = "1"  
>   
>  More Info [MS KB135586](http://support.microsoft.com/kb/135586 "Hiding the Last Logged On User Name in Windows 95 [Q135586]")

 Prevent caching of passwords in pwl files (Will also forget dialup passwords):
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Network\]  
>  DisablePwdCaching = 1  
>   
>  More Info [MS KB137826](http://support.microsoft.com/kb/137826 "Disabling Password Caching and Changing Passwords [Q137826]")  
>  More Info [MS KB141858](http://support.microsoft.com/kb/141858 "No Windows or Network Logon Dialog Box at Startup [Q141858]")  
>  More Info [MS KB148925](http://support.microsoft.com/kb/148925 "Dial-Up Networking Password Is Not Saved [Q148925]")

 Prevent logon unless authenticated by the domain: (This can also be configured with Poledit -&gt; Default computer -&gt; Windows 95 network -&gt; logon -&gt; "Require validation by network for windows access")
> \[HKEY\_LOCAL\_MACHINE \\Network \\Logon\]  
>  MustBeValidated = 1