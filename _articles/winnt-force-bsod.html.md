---
title: 'Provoke a blue screen of death on command'
date: '2001-09-03T20:27:01+02:00'
permalink: /article/winnt-force-bsod.html
author: Snakefoot
excerpt: 'Using a special keyboard shortcut to create a blue screen of death with memory dump.'
type: post
id: 388
categories:
    - windows-2003-tips
    - windows-xp-tips
    - windows-2000-tips
tags:
    - blue-screen-of-death
    - keyboard
    - memory-dump
    - shortcut-keys
---
It is possible to force a Blue Screen of Death (BSOD) if this is needed. It can be useful when testing the recovery abilities of your 3rd party application or cluster service.  
  
 To activate this create this new DWORD in the registry:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\i8042prt \\Parameters\]  
>  CrashOnCtrlScroll=1

 After making the change and performed a reboot, then hold down the right CTRL key and press ScrollLock Twice (Doesn't work with USB keyboards). It will cause a BSOD with the following message:  
> MANUALLY\_INITIATED\_CRASH (0xE2)

 More info [MS KB244139](http://support.microsoft.com/kb/244139 "Windows Feature Allows a Memory.dmp File to Be Generated with Keyboard [Q244139]")