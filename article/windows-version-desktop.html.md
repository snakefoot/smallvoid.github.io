---
title: 'Display the Windows version on the desktop'
date: '2001-01-21T23:45:58+01:00'
status: publish
permalink: /article/windows-version-desktop.html
author: Snakefoot
excerpt: 'When BETA testing Windows versions then it can be rather useful to easily see the build version on the desktop.'
type: post
id: 296
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - Desktop
    - visual-style
    - windows-version
post_format: []
tags:
    - 'desktop,windows-version,visual-style'
---
You can have the version number of your Windows shown on your desktop. This is done through the registry, by changing this DWORD value

> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  PaintDesktopVersion=1

 Note this will not work when using active desktop.  
  
 Note another solution is to use [BgInfo](/article/windows-bginfo.html) that changes the wallpaper so it includes the system information of the computer. Or use [Samurize](/article/windows-samurize-desktop.html) that can manipulate the desktop like it was a HTML page and can display the system information on the desktop.  
  
 More Info [MS KB315420](http://support.microsoft.com/kb/315420 "HOW TO: Display the Build Number on the Desktop in Windows 2000 [Q315420]")