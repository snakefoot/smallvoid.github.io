---
title: 'Configure the login and welcome screen in Windows XP'
date: '2002-06-25T00:20:36+02:00'
status: publish
permalink: /article/winxp-welcome-screen.html
author: Snakefoot
excerpt: 'How to enable the Welcome Screen and specify what users to display at logon.'
type: post
id: 155
category:
    - 'User Security'
tag:
    - welcome-screen
post_format: []
tags:
    - welcome-screen
---
With WinXP a new way of how to logon was created, it involved showing all user accounts along with a fancy icon. Only requiring one to click the icon to login.  
  
 To change the login to the standard logon box, go to "Control Panel" -&gt; "User Accounts" -&gt; "Change the way users log on or off" and uncheck "Use the welcome screen for fast and easy logon". It should be reflected in this registry key.

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon\]  
>  LogonType = 0 (Classic = 0, Welcome Screen = 1, Default = 1)  
>   
>  More Info [MS KB291559](http://support.microsoft.com/kb/291559 "HOW TO: Change the Logon Window and the Shutdown Preferences in Windows XP [Q291559]")  
>   
>  Note when the Welcome Screen is enabled and [Require CTRL + ALT + DEL at logon](http://support.microsoft.com/kb/291559 "How to change the logon window and the shutdown preferences in Windows XP [Q291559]") is disabled (DisableCAD), then it is not possible to lock the computer again using CTRL+ALT+DEL, but it will instead start Task Manager. More Info [MS KB281980](http://support.microsoft.com/kb/281980 "Using CTRL+ALT+DEL key combination to open Windows Security opens Task Manager [Q281980]")

 Note it is possible to momentarily change the Welcome Screen to the standard logon screen, by holding down the keys CTRL and ALT while pressing DEL twice. This can be useful if needing to login with a "hidden" account not shown on the Welcome Screen. In WinXP Pro it can used to login with the builtin Administrator account.  
  
<a name="SPECIALACCOUNTS"></a> Note it is possible to configure what users should be presented on the Welcome Screen. By standard all but special system accounts are displayed on the Welcome Screen. One can hide an account from the welcome screen or force a hidden system account to appear by adding a DWORD registry key with the username:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\Winlogon \\SpecialAccounts \\UserList\]  
>  Administrator = 1 (Visible = 1, Hidden =0)  
>   
>  More Info [MS KB827072](http://support.microsoft.com/kb/827072 "PRB: Welcome to Windows Screen Appears When You Start Windows XP After You Install the .NET Framework 1.1 [Q827072]")  
>   
>  Note in WinXP Home one can only access the builtin Administrator account if booting into safemode. By default the builtin Administrator account has no password.  
>   
>  Note in WinXP Pro the Administrator account is only shown on the Welcome Screen, if no other account is part of the Administrator-Group. One can still login using the account if holding down CTRL+ALT and pressing DEL twice.  
>   
>  Note in WinXP an account is only shown on the Welcome Screen, if it belongs to either of these groups Administrators, Power Users, or Users.

 Related [Configure Automatic Logon](/article/winnt-automatic-logon.html)  
 Related [Advanced User Management in Windows XP Home](/article/winxp-home-usermgt.html)  
 Related [Appearence of the login and welcome screen in WinXP](/article/winxp-login-welcome.html)  
  
 More Info [MS KB279783](http://support.microsoft.com/kb/279783 "HOW TO: Create and Configure User Accounts in Windows XP [Q279783]")  