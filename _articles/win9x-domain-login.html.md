---
title: 'Configure a secure network login to a domain'
date: '2003-09-08T21:37:57+02:00'
permalink: /article/win9x-domain-login.html
author: Snakefoot
excerpt: 'Forcing the user to provide credentials before being allowed to use Windows 9x.'
type: post
id: 215
categories:
    - windows-95_network
    - windows-98_network
    - windows-me_network
tags:
    - user-account
    - windows-domain
    - windows-login
---
Clear the username of the previous logged on user, so it is not displayed to the next user (Will disable [Automatic Login](/article/win9x-automatic-login.html)):

> \[HKEY\_LOCAL\_MACHINE \\Network \\Logon\]  
>  DontShowLastUser = "1"  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20135586%20Q135586" rel="nofollow" title="Hiding the Last Logged On User Name in Windows 95 [Q135586]">MS KB135586</a>

 Prevent caching of passwords in pwl files (Will also forget dialup passwords):
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Network\]  
>  DisablePwdCaching = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20137826%20Q137826" rel="nofollow" title="Disabling Password Caching and Changing Passwords [Q137826]">MS KB137826</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20141858%20Q141858" rel="nofollow" title="No Windows or Network Logon Dialog Box at Startup [Q141858]">MS KB141858</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20148925%20Q148925" rel="nofollow" title="Dial-Up Networking Password Is Not Saved [Q148925]">MS KB148925</a>

 Prevent logon unless authenticated by the domain: (This can also be configured with Poledit -&gt; Default computer -&gt; Windows 95 network -&gt; logon -&gt; "Require validation by network for windows access")
> \[HKEY\_LOCAL\_MACHINE \\Network \\Logon\]  
>  MustBeValidated = 1