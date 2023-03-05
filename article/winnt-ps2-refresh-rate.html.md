---
title: 'Changing PS/2 mouse refresh rate'
date: '2001-01-01T13:08:03+01:00'
status: publish
permalink: /article/winnt-ps2-refresh-rate.html
author: Snakefoot
excerpt: 'Improve the precision and smoothness of your ps/2 device by increasing the sample rate.'
type: post
id: 36
category:
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - mouse
    - ps2
    - refresh-rate
    - sample-rate
post_format: []
tags:
    - 'ps2,mouse,refresh-rate,sample-rate'
---
The computer mouse have a certain DPI(Dot Per Inch)/CPI(Count Per Inch), which describes how precise it is at detecting changes in the position (Ex. 800 DPI). Every time the mouse detects a change in position, then it reports the new position to the computer using the port it is attached to (Serial/PS2/USB). The computer checks the mouse-port at a certain interval (refresh-rate), and processes the reports the mouse have made since the last check. If the refresh-rate is too low (&lt;100 Hz), then it can give feeling of having a jerky mouse.  
  
 The overall refresh-rate cannot get better than the refresh-rate (CRT) or response-time (LCD) of the monitor, but it is possible for the mouse-refresh rate to get out of sync with the monitor-refresh rate. This can also lead to a jerky feeling.

- Mouse position is updated (Every 8 ms = 125 Hz)
- 8 ms
- Monitor displays mouse position (Every 10 ms = 100 Hz)
- Mouse position is updated
- 8 ms
- Mouse position is updated
- 2 ms
- Monitor displays mouse position (Seems jerky because of two position jumps in between)
 
 To minimize this problem one should double the refresh rate of the mouse or the monitor. It is usual easier to change the refresh-rate of the mouse. - WinNT4: Change the PS/2 refresh rate with this registry key (REG\_DWORD):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\i8042prt \\Parameters\]  
  >  SampleRate=200 (A value from 1-200 Hz and 60 Hz is the default)  
  >   
  >  More Info [MS KB102989](http://support.microsoft.com/kb/102989 "REG: Device Driver Entries, PART 2--Mouse/Keyboard Driver [Q102989]")
- Win2k: Change the PS/2 refresh rate using the Mouse applet in the Control Panel.
- WinXP: Change the PS/2 refresh rate at Control Panel -&gt; Mouse -&gt; Hardware-tab -&gt; Select "PS/2 Compatible Mouse" -&gt; Properties-button -&gt; Advanced Settings-tab -&gt; Sample Rate.
 
 Note for an USB mouse the refresh rate is usually 125 Hz, which is hardcoded into the USB driver and requires one to modify the USB driver. It is many times easier just to use an USB-&gt;PS/2 adapter and change the PS/2 refresh rate to 200 Hz.  
  
 Note the USB controller is polled every 1 millisec (1000 Hz), and there is an option that can lower the polling rate to every 5 millisec (200 hz), which can be necessary if having a laptop that is having problems entering powersafe mode.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Class \\{36FC9E60-C465-11CF-8056-444553540000} \\0000\]  
>  IdleEnable = 1 (0 = 1000 Hz, 1 = 200 Hz, Default = 0)  
>   
>  More Info [MS KB297045](http://support.microsoft.com/kb/297045 "The Laptop Computer May Be Unable to Enter the C3 Processor Power-Saving State [Q297045]")

 Related [MouseRate](http://www.tscherwitschke.de/ "Mouse Rate Checker by Oliver Tscherwitschke ") (Will display the current refresh-rate of the mouse)