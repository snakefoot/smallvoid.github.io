---
title: 'Change the looks of the login and welcome screen'
date: '2005-09-25T23:20:06+02:00'
permalink: /article/winxp-login-welcome.html
author: Snakefoot
excerpt: 'Changing the visual styles of the login and shutdown screens.'
type: post
id: 156
categories:
    - windows-xp_tips
tags:
    - desktop
    - welcome-screen
    - windows-login
---
When using the Welcome Screen then there are different ways to change its appearence. For example one can use a picture/icon to identify each account. To add different pictures than the ones provided by Microsoft, place the new pictures (48x48 pixels, gif,bmp,jpg) in this folder:

> C:\\Documents And Settings\\All Users\\Application Data\\Microsoft\\User Account Pictures\\Default Pictures  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20292434%20Q292434" rel="nofollow" title="HOW TO: Add or Change a User's Picture in Windows XP [Q292434]">MS KB292434</a>

 The Welcome Screen allows one to see if there are any unread email for a certain account. It is possible to disable this feature:  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\UnreadMail\]  
>  MessageExpiryDays = 0  
>   
>  Note if having the feature enabled, but the unread e-mail count is wrong, then try to reset the count (Same as Repair unread mail count in Tweak UI):  
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\UnreadMail\]  
>  Message Count = 0  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20304148%20Q304148" rel="nofollow" title="Overview of the Mail Notification Display on the Windows XP Welcome Screen [Q304148]">MS KB304148</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20831403%20Q831403" rel="nofollow" title="Description of the Outlook Unread Mail Count functionality in Outlook 2003 [Q831403]">MS KB831403</a>

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