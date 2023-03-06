---
title: 'Configure the taskbar Start Menu'
date: '2003-01-01T22:28:27+01:00'
status: publish
permalink: /article/windows-start-menu.html
author: Snakefoot
excerpt: 'Changing the behavior and visual appearance of the Start Menu.'
type: post
id: 301
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - start-menu
    - taskbar
post_format: []
tags:
    - 'start-menu,taskbar'
---
Speed up the start menu by configuring the delay before a folder in the Start Menu is shown:

> This can also be configured with the PowerToy TweakUI [Win9x/WinNT4/Win2k](/article/win95-power-toys.html), [WinXP](/article/winxp-power-toys.html).  
>   
>  \[HKEY\_CURRENT\_USER\\ Control Panel\\ desktop\]  
>  MenuShowDelay = 50 (Default 400 ms)

 Configure whether to scroll the Start Menu or use multiple columns (Requires Active Desktop):
> \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Windows\\ CurrentVersion\\ explorer \\Advanced\]  
>  StartMenuScrollPrograms = "false" (Default="true")

 Configure whether to use Personalized Menus and hide programs not often used (WinMe/2k/Xp)
> Win2k: Start Menu -&gt; Settings -&gt; Taskbar &amp; Start Menu -&gt; Untick "Use Personalized Menus"  
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  IntelliMenus = "No" ("Yes"=Enabled, "No"=Disabled)

 More Info [MS KB214831](http://support.microsoft.com/kb/214831 "When You Point to a Menu the Submenu May Not Appear [Q214831]")  
 More Info [MS KB257128](http://support.microsoft.com/kb/257128 "Enable Personalized Favorites Menu Feature Does Not Take Effect Immediately [Q257128]")  