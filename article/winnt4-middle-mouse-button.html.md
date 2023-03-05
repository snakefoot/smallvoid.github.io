---
title: 'Enable the middle mouse button'
date: '2000-01-01T12:53:13+01:00'
status: publish
permalink: /article/winnt4-middle-mouse-button.html
author: Snakefoot
excerpt: 'How to enable the 3rd mouse button, so it can be used in applications and games.'
type: post
id: 35
category:
    - Tips
tag:
    - mouse
post_format: []
tags:
    - mouse
---
By default it only recognizes the left and the right mouse button, but one can activate the 3rd mouse button (or middle mouse button), which ex. then can be used to perform a double-click.  
  
 Edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\ PORT-TYPE-X\]  
>  NumberOfButtons=3  
>   
>  PORT-TYPE-X should be exchanged with the type of mouse connection: "BUSMOUSE", "SERMOUSE", or "i8042PRT" (PS/2).

 More info [MS KB102988](http://support.microsoft.com/kb/102988 "REG: Device Driver Entries, PART 1 [Q102988]")  
 More info [MS KB102989](http://support.microsoft.com/kb/102989 "Device Driver Entries, PART 2--Mouse/Keyboard Driver [Q102989]")  
 More info [MS KB102990](http://support.microsoft.com/kb/102990 "Device Driver Entries, PART 3--Mouse/Keyboard Driver [Q102990]")  