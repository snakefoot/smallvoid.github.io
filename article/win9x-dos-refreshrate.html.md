---
title: 'Configure the DOS prompt refresh rate within Windows'
date: '2000-01-01T22:39:23+01:00'
status: publish
permalink: /article/win9x-dos-refreshrate.html
author: Snakefoot
excerpt: 'Increasing the DOS prompt refresh rate to make the display smoother.'
type: post
id: 165
category:
    - Tips
    - Tips
    - Tips
tag: []
post_format: []
---
Windows 9x makes it possible to open a DOS prompt without leaving Windows. The DOS prompt is almost like any other window, except that the window is polled for changes with a certain time interval.  
  
 By default the DOS prompt is updated every 50 millisecond (20 fps). This limit can be seen when text is scrolling in the DOS prompt.  
  
 To configure the time in milliseconds between each update, change this SYSTEM.INI setting in the \[386Enh\] section:

> \[386Enh\]  
>  WindowsUpdateTime=10