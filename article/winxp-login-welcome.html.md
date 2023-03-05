---
title: 'Change the looks of the login and welcome screen'
date: '2005-09-25T23:20:06+02:00'
status: publish
permalink: /article/winxp-login-welcome.html
author: Snakefoot
excerpt: 'Changing the visual styles of the login and shutdown screens.'
type: post
id: 156
category:
    - Desktop
tag:
    - welcome-screen
    - windows-login
post_format: []
tags:
    - 'windows-login,welcome-screen'
---
When using the Welcome Screen then there are different ways to change its appearence. For example one can use a picture/icon to identify each account. To add different pictures than the ones provided by Microsoft, place the new pictures (48x48 pixels, gif,bmp,jpg) in this folder:

> C:\\Documents And Settings\\All Users\\Application Data\\Microsoft\\User Account Pictures\\Default Pictures  
>   
>  More Info [MS KB292434](http://support.microsoft.com/kb/292434 "HOW TO: Add or Change a User's Picture in Windows XP [Q292434]")

 The Welcome Screen allows one to see if there are any unread email for a certain account. It is possible to disable this feature:  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\UnreadMail\]  
>  MessageExpiryDays = 0  
>   
>  Note if having the feature enabled, but the unread e-mail count is wrong, then try to reset the count (Same as Repair unread mail count in Tweak UI):  
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\UnreadMail\]  
>  Message Count = 0  
>   
>  More Info [MS KB304148](http://support.microsoft.com/kb/304148 "Overview of the Mail Notification Display on the Windows XP Welcome Screen [Q304148]")  
>  More Info [MS KB831403](http://support.microsoft.com/kb/831403 "Description of the Outlook Unread Mail Count functionality in Outlook 2003 [Q831403]")

 The Welcome Screen can also show how many programs other users are running, when using [Fast User Switching](/article/winnt-services-fus.html). To disable the diplay of Program Running, set the following registry key to 0 and change its permissions to read-only:
> \[HKEY\_CURRENT\_USER \\SessionInformation\]  
>  ProgramCount = 0

 The theme on the login and shutdown dialog (When not using the Welcome Screen) can be changed to your favorite theme. This is done by configuring the theme for the .DEFAULT user:
> \[HKEY\_USERS \\.DEFAULT \\Software \\Microsoft \\Windows \\CurrentVersion \\ThemeManager\]  
>  ColorName = "Metallic" (Default = "NormalColor")

 The theme on the login and shutdown dialog (When not using the Welcome Screen) can be disabled, so it becomes Windows 2000 style:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\ThemeManager\]  
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\ThemeManager\]  
> \[HKEY\_USERS\\.DEFAULT \\Software \\Microsoft \\Windows \\CurrentVersion \\ThemeManage\]  
> ThemeActive = 0 (Default = 1)

 Related [Configure the login and welcome screen in WinXP](/article/winxp-welcome-screen.html)