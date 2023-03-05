---
title: 'Configure automatic login in Windows 9x'
date: '2003-05-25T21:34:21+02:00'
status: publish
permalink: /article/win9x-automatic-login.html
author: Snakefoot
excerpt: 'Enabling automatic login so one doesn''t have to type username and password at every boot.'
type: post
id: 214
category:
    - Network
    - Network
    - Network
tag:
    - automatic-login
    - user-account
    - user-profile
    - windows-login
post_format: []
tags:
    - 'automatic-login,user-profile,user-account,windows-login'
---
It is possible to have several user profiles in Win9x. This gives the possibility for each user to have their own personal settings for Desktop, Start Menu, Favorites, My Documents, etc. By standard there is only a single user profile, which is automatically logged in.  
  
 If having Network Neighborhood installed then it might request for login, but it can be disabled:

- Open **Control Panel** and double click the **Network**-applet
- Select the **Configuration**-tab
- change the dropdown **Primary Network Logon** from **Client for Microsoft Network** to **Windows Logon**
 
 If having several user accounts and want one to be automatically logged in (This can also be done with the PowerToy TweakUI):
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Winlogon\]  
>  AutoAdminLogon = "1"  
>  DefaultUsername = "username"  
>  DefaultPassword = "password"  
>   
>  Note requires that [username of the previous user is NOT cleared](/article/win9x-domain-login.html).

 More info [MS KB152104](http://support.microsoft.com/kb/152104 "How to Prevent a Windows 95, Windows 98, or Windows Me Logon Prompt at Startup [Q152104]")