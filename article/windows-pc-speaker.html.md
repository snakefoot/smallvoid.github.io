---
title: 'Turn off the beeping from the PC Speaker'
date: '2003-06-22T01:11:01+02:00'
status: publish
permalink: /article/windows-pc-speaker.html
author: Snakefoot
excerpt: 'Disable the beep from the PC speaker when Windows performs an alert.'
type: post
id: 277
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - pc-speaker
post_format: []
tags:
    - pc-speaker
---
Some applications in Windows can be rather annoying as they sometimes generates beeps in the PC Speaker for every action they make. It is very noticeable when using a mobile computer where the PC speaker is right in your face. One can disable this beeping through the registry:

> \[HKEY\_CURRENT\_USER \\Control Panel \\Sound\]  
>  Beep = "No" (Enabled = "Yes")  
>   
>  Note if using Win2k/WinXP then one can also use the **Device manager** to disable the **Non-Plug and Play Driver** called **Beep** (Hidden Device).

 Note to configure the sounds played by your soundcard use the Control Panel and open the following applet:
- Sounds (Win95/98)
- Sounds and Multimedia (WinMe)
- Sound Schemes (WinNT4)
- Sounds and multimedia (Win2k)
- Sounds and Audio Devices (WinXP)