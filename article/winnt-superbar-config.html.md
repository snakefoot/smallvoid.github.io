---
title: 'Configure the taskbar in Windows 7'
date: '2009-09-21T00:34:41+02:00'
status: publish
permalink: /article/winnt-superbar-config.html
author: Snakefoot
excerpt: 'Windows 7 introduces a new taskbar design (aka. superbar), that should make it easier to keep track of applications.'
type: post
id: 812
category:
    - Desktop
tag:
    - aero
    - taskbar
post_format: []
tags:
    - 'taskbar,aero'
---
##### Control thumbnail preview

 When hovering the mouse over an application in the taskbar, then it will display a small thumbnail image of the application window.  
  
 Create this DWORD key to control the delay before showing the thumbnail:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  ThumbnailLivePreviewHoverTime = 50 (Time in miliseconds)

 Note by setting it to a very high value, then it will seem like the application thumbnail is disabled.
 
##### Control live preview

 When hovering the mouse over an application in the taskbar then it will display a live preview of the whole window (Aka. Aero Peek).  
  
 Create this DWORD key to control the delay before showing the live preview:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  ExtendedUIHoverTime = 200 (Time in miliseconds - Default 400 ms)

 Note by setting it to a very high value, then it will seem like the application preview is disabled.  
  
 Credits [WinGeek.com](http://wingeek.com/articles/39445/adjust-taskbar-preview-hover-delay/)