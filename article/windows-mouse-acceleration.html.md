---
title: 'Configure Mouse Acceleration'
date: '2002-10-13T01:45:22+02:00'
status: publish
permalink: /article/windows-mouse-acceleration.html
author: Snakefoot
excerpt: 'Mouse is accelerated when moved in a single movement to make the Windows nagivation easier.'
type: post
id: 279
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - mouse
    - mouse-acceleration
post_format: []
tags:
    - 'mouse,mouse-acceleration'
---
If not satisfied with the possibilities of the Mouse-Applet in the Control Panel, then one can configure the acceleration with these DWORD registry values :

> \[HKEY\_CURRENT\_USER \\Control Panel \\Mouse\]  
>  MouseThreshold1 = 7 (Amount of pixels to move before going 2x normal-speed)  
>  MouseThreshold2 = 0 (Amount of pixels to move before going 4x normal-speed)  
>  MouseSpeed = 1 (0 = Disabled, 1 = Uses Threshold1, 2 = Uses Threshold1+2)

 <table border="1" cellpadding="4"><tr><td> </td><td>Disable</td><td>Low</td><td>Medium</td><td>High</td><td>Enhanced Pointer Position</td></tr><tr><td>MouseThreshold1</td><td>0</td><td>7</td><td>4</td><td>4</td><td>6</td></tr><tr><td>MouseThreshold2</td><td>0</td><td>0</td><td>12</td><td>6</td><td>10</td></tr><tr><td>MouseSpeed</td><td>0</td><td>1</td><td>2</td><td>2</td><td>1</td></tr></table>

  
 More Info [MS KB102978](http://support.microsoft.com/kb/102978 "User Preferences Entries, PART 3 [Q102978]")  
 More Info [MS KB149228](http://support.microsoft.com/kb/149228 "How to Disable Mouse Acceleration [Q149228]")  
  
 Note if the mouse pointer moves erratically or does not respond, then it might be caused by having multiple mouse drivers installed. More Info [MS KB321122](http://support.microsoft.com/kb/321122 "The Microsoft mouse pointer moves erratically or does not respond when you use a Microsoft pointing device [Q321122]")  
  
 Credits [franck.kiechel.free.fr](http://franck.kiechel.free.fr/ "Franck Kiechel")