---
title: 'Configure Mouse Acceleration in WinXP'
date: '2002-10-13T22:23:29+02:00'
status: publish
permalink: /article/winnt-mouse-acceleration.html
author: Snakefoot
excerpt: 'The settings to configure mouse acceleration are hidden away but can still be changed.'
type: post
id: 399
category:
    - Tips
tag:
    - mouse
post_format: []
tags:
    - mouse
---
For some reason Microsoft decided that it should not be possible to configure Mouse Acceleration in WinXP when using the Mouse-Applet in the Control Panel (It is possible in Win2k).  
  
 Many have solved the problem by downloading the manufactures(Microsoft Intellipoint, Logitech MouseWare, etx) latest drivers for their mouse and used the manufactures software to configure acceleration.  
  
 There is a rumor that hardware mouse-acceleration is always enabled, to disable this, apply the following to the registry (Remember to make a backup of your current values before applying) :

> Windows Registry Editor Version 5.00  
>   
>  \[HKEY\_CURRENT\_USER\\Control Panel\\Mouse\]  
>  "SmoothMouseXCurve"=hex:00,00,00,00,00,00,00,00,00,a0,00,00,00,00,00,00,00,40,\\  
>  01,00,00,00,00,00,00,80,02,00,00,00,00,00,00,00,05,00,00,00,00,00  
>  "SmoothMouseYCurve"=hex:00,00,00,00,00,00,00,00,66,a6,02,00,00,00,00,00,cd,4c,\\  
>  05,00,00,00,00,00,a0,99,0a,00,00,00,00,00,38,33,15,00,00,00,00,00

 If wanting to change the mouse acceleration settings back to default, then either delete **SmoothMouseXCurve** and **SmoothMouseYCurve** and reboot, or apply these settings:
> Windows Registry Editor Version 5.00  
>   
>  \[HKEY\_CURRENT\_USER\\Control Panel\\Mouse\]  
>   
>  "SmoothMouseXCurve"=hex:00,00,00,00,00,00,00,00,15,6e,00,00,00,00,00,00,00,40,\\  
>  01,00,00,00,00,00,29,dc,03,00,00,00,00,00,00,00,28,00,00,00,00,00  
>  "SmoothMouseYCurve"=hex:00,00,00,00,00,00,00,00,b8,5e,01,00,00,00,00,00,cd,4c,\\  
>  05,00,00,00,00,00,cd,4c,18,00,00,00,00,00,00,00,38,02,00,00,00,00

 The WinXP Mouse-Applet lacks the ability to change the software acceleration, besides turning it off by disabling "Enhanced Pointer Position", but one can [configure mouse acceleration through the registry](/article/windows-mouse-acceleration.html).