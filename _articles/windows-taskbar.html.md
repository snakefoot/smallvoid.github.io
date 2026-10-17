---
title: 'Configure the Windows taskbar'
date: '2003-07-04T23:58:43+02:00'
permalink: /article/windows-taskbar.html
author: Snakefoot
excerpt: 'Changing the behavior and visual appearance of the task bar.'
type: post
id: 304
categories:
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
    - windows-2003_tips
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
tags:
    - desktop
    - windows-explorer
    - quick-launch
    - taskbar
---
Disable the arrow with "Click here to begin" in Win95/NT4:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoStartBanner = 01 00 00 00 (BINARY if Win95)  
>  NoStartBanner = 1 (DWORD if WinNT4)

 Disable Tip of the day:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer \\Tips\]  
>  Show= 00 00 00 00 (BINARY if Win95/WinNT4)  
>  Show= 0 (DWORD if Win2k/WinXP)

 There is block to prevent another window to steal focus when f.ex. writing an email in the front window. One can configure the time in milisecs, which should pass after the user have made input to the active window before another window is allowed to automatically become front window:
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  ForegroundLockTimeout = 200000 (0 = A window can steal focus right away)  
>   
>  Note if using a lousy popup-stopper or infected by spy-/ad-/mal-ware, then one might also experience focus stealing.

 In the situation where an application is not allowed automatically to take focus, then the application will blink in the taskbar instead. On can specify how many times it should blink:
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  ForegroundFlashCount = 3 (0 = Blink until clicked)

 Disable the Active Desktop features on taskbar like Quick Launch toolbar (aka. "Shell Enhancements" in [TweakUI](/article/win95-power-toys.html)):
> \[HKEY\_CURRENT\_USER \\Control Panel \\Desktop\]  
>  ClassicShell = 01 00 00 00 (BINARY)  
>   
>  More Info [MS KB273785](http://support.microsoft.com/kb/273785 "Quick Launch Toolbar Icons Are Missing or Unavailable [Q273785]")