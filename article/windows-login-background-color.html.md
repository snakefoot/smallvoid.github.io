---
title: 'Changing the background color for the login screen'
date: '2001-01-01T22:11:23+01:00'
status: publish
permalink: /article/windows-login-background-color.html
author: Snakefoot
excerpt: 'Changing the color of the desktop shown before a user has logged in.'
type: post
id: 300
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - visual-style
    - windows-login
post_format: []
tags:
    - 'windows-login,visual-style'
---
If you have become tired of the standard color on you background at login then this might be the thing for you.  
  
 Edit the registry and add/update this (STRING):

> \[HKEY\_USERS \\.DEFAULT \\Control Panel \\Colors\]  
>  Background="58 110 165" (default)

 The colour is configured using these settings:  
  
<table border="1"><tr><th>Color</th> <th>Red</th><th>Green</th><th>Blue</th></tr><tr><td style="color:#FFFFFF">white</td> <td>255</td><td>255</td> <td>255</td></tr><tr><td style="color:#FF0000">Red</td> <td>255</td><td>0</td> <td>0</td></tr><tr><td style="color:#FFFF00">Yellow</td> <td>255</td><td>255</td> <td>0</td></tr><tr><td style="color:#00FF00">Green</td> <td>0</td> <td>255</td> <td>0</td></tr><tr><td style="color:#00FFFF">Cyan</td> <td>0</td> <td>255</td> <td>255</td></tr><tr><td style="color:#0000FF">Blue</td> <td>0</td> <td>0</td> <td>255</td></tr><tr><td style="color:#FF00FF">Magenta</td><td>255</td><td>0</td> <td>255</td></tr><tr><td style="color:#000000">Black</td> <td>0</td> <td>0</td> <td>0</td></tr></table>

  
 One can also [change the background Wallpaper](/article/windows-wallpaper.html) for the login screen, just use:
 > \[HKEY\_USERS \\.DEFAULT\]

 Instead of:
 > \[HKEY\_CURRENT\_USER\]

 More Info [MS KB103327](http://support.microsoft.com/kb/103327 "Changing Background Bitmap for the Windows NT Logon Screen [Q103327]")  