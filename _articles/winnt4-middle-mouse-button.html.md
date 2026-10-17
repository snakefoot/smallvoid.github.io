---
title: 'Enable the middle mouse button'
date: '2000-01-01T12:53:13+01:00'
permalink: /article/winnt4-middle-mouse-button.html
author: Snakefoot
excerpt: 'How to enable the 3rd mouse button, so it can be used in applications and games.'
type: post
id: 35
categories:
    - windows-nt4_tips
tags:
    - mouse
---
By default it only recognizes the left and the right mouse button, but one can activate the 3rd mouse button (or middle mouse button), which ex. then can be used to perform a double-click.  
  
 Edit this DWORD registry key:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\ PORT-TYPE-X\]  
>  NumberOfButtons=3  
>   
>  PORT-TYPE-X should be exchanged with the type of mouse connection: "BUSMOUSE", "SERMOUSE", or "i8042PRT" (PS/2).

 More info <a href="https://www.bing.com/search?q=KB%20102988%20Q102988" rel="nofollow" title="REG: Device Driver Entries, PART 1 [Q102988]">MS KB102988</a>  
 More info <a href="https://www.bing.com/search?q=KB%20102989%20Q102989" rel="nofollow" title="Device Driver Entries, PART 2--Mouse/Keyboard Driver [Q102989]">MS KB102989</a>  
 More info <a href="https://www.bing.com/search?q=KB%20102990%20Q102990" rel="nofollow" title="Device Driver Entries, PART 3--Mouse/Keyboard Driver [Q102990]">MS KB102990</a>  