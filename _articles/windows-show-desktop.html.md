---
title: 'Creating the Show Desktop shortcut'
date: '2001-01-01T23:27:30+01:00'
permalink: /article/windows-show-desktop.html
author: Snakefoot
excerpt: 'The Show Desktop shortcut in the quick launch bar can be restored if deleted.'
type: post
id: 295
categories:
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
    - windows-2003_tips
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
    - windows-vista_tips
tags:
    - desktop
    - windows-explorer
    - link-shortcut
    - quick-launch
    - show-desktop
---
Active Desktop includes a feature that allows one to minimize all active Windows, so one can easily access the icons on the desktop. The feature is called "Show Desktop" and is accessed through an icon on the Quicklaunch bar.  
  
 If missing the "Show Desktop" icon from your Quicklaunch bar, then one can restore / recover / repair / recreate it again by making a TEXT-file with the following contents:

> \[Shell\]  
>  Command=2  
>  IconFile=explorer.exe,3  
>  \[Taskbar\]  
>  Command=ToggleDesktop

 Save the file as "Show Desktop.scf" and then hold down right mouse button while dragging the file into your Quick Launch bar, and do a Copy/Move here.  
  
 Note on WinXP/Vista the task bar can be "Locked" (Right click the task-bar to unlock). The Quick Launch-bar cannot be resized when when "Locked", so items might be hidden when having many items in the Quick Launch-bar.  
  
 Note to create your own Send-To "Desktop (create shortcut)", create a new text-file and rename it "Desktop (create shortcut).desklink" (Or copy it from the Send To folder for the Default user).  
  
 More Info <a href="https://www.bing.com/search?q=KB%20190355%20Q190355" rel="nofollow" title="How to Re-create the Show Desktop Icon on Quick Launch Toolbar [Q190355]">MS KB190355</a>  