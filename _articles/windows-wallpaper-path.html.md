---
title: 'Change path of where Windows looks for wallpapers'
date: '2002-03-30T00:56:16+01:00'
permalink: /article/windows-wallpaper-path.html
author: Snakefoot
excerpt: 'Change the default wallpaper folder used when changing the wallpaper in Windows.'
type: post
id: 275
categories:
    - windows-95-tips
    - windows-98-tips
    - windows-me-tips
    - windows-nt4-tips
tags:
    - wallpaper
---
By default Windows looks for wallpapers in the Windows folder. In WinNT one could change this to the [environment variable](/article/winnt-environment-variables.html) %USERPROFILE%.  
  
 To change the path, update this registry key:

> \[HKEY\_LOCAL\_MACHINE \\ Software \\ Microsoft \\ Windows \\ CurrentVersion\]  
>  WallPaperDir = "C:\\My Documents"

 Credits [krzywanek.de](http://krzywanek.de/)