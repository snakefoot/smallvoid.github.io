---
title: 'Disable the blur-effect of the glass window border'
date: '2009-10-21T00:34:30+02:00'
status: publish
permalink: /article/winnt-transparent-border.html
author: Snakefoot
excerpt: 'How to disable blurring of windows in the background, and get full clear glass transparency.'
type: post
id: 819
category:
    - Desktop
tag:
    - aero
post_format: []
tags:
    - aero
---
The border around the windows are transparent using the glass effect. When placing one window on top of another then the background window becomes blurred, so it is easy to see what window has focus.  
  
 To disable the blurring the of the background windows with this DWORD registry value:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\DWM\]  
>  ColorizationGlassReflectionIntensity = 0 (0 = No blur, Default = 50)

 After having changed the registry value, then change the theme to Basic (notice blur is gone), then change to the wanted theme (the blur remains gone).  
  
 Credits [Tweaking with Vishal](http://www.askvg.com/how-to-disable-window-borders-blur-in-windows-7/)