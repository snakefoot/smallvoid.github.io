---
title: 'Display the Windows version on the desktop'
date: '2001-01-21T23:45:58+01:00'
permalink: /article/windows-version-desktop.html
author: Snakefoot
excerpt: 'When BETA testing Windows versions then it can be rather useful to easily see the build version on the desktop.'
type: post
id: 296
categories:
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
    - windows-2003_tips
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
tags:
    - desktop
    - windows-explorer
    - visual-style
    - windows-version
---
You can have the version number of your Windows shown on your desktop. This is done through the registry, by changing this DWORD value

> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  PaintDesktopVersion=1

 Note this will not work when using active desktop.  
  
 Note another solution is to use [BgInfo](/article/windows-bginfo.html) that changes the wallpaper so it includes the system information of the computer. Or use [Samurize](/article/windows-samurize-desktop.html) that can manipulate the desktop like it was a HTML page and can display the system information on the desktop.  
  
 More Info <a href="https://www.bing.com/search?q=KB+315420+Q315420" rel="nofollow" title="HOW TO: Display the Build Number on the Desktop in Windows 2000 [Q315420]">MS KB315420</a>