---
title: 'Create keyboard shortcut to quickly launch a program'
date: '2001-01-01T12:15:54+01:00'
status: publish
permalink: /article/windows-keyboard-shortcuts.html
author: Snakefoot
excerpt: 'How to configure a keyboard shortcut as a hotkey to quickly start an application.'
type: post
id: 240
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - keyboard
    - shortcut-keys
    - windows-key
post_format: []
tags:
    - 'shortcut-keys,windows-key,keyboard'
---
If you have an utility that you start frequently (Like the command prompt or regedit), then you might want to assign a shortcut-key for launching it.  
  
 To assign a hot key for an application:

1. Make a shortcut-link to the application (This will also allow you to start the application with certain parameters)
2. Place the shortcut-link on desktop or Start-menu (The QuickLaunch-bar will not work)
3. Right-click the created shortcut-link and select the fan "Shortcut"
4. Assign the hotkey by giving focus to the edit-field "Shortcut Key", and press the key-combination
5. Press "Ok"-button
 
 Note one might experience long delays of 3 secs or more, when hitting the shortcut key before the application actually opens. This is because when hitting the shortcut key, then Windows Explorer checks if the application is already open, and if so Windows Explorer gives focus to the open application. The problem is that Windows Explorer needs to ask each open application whether it has the shortcut key assigned, and if some random application is not responding, then it will cause delays. More Info [oldnewthing](http://blogs.msdn.com/b/oldnewthing/archive/2012/05/02/10299709.aspx)  
  
 Related [Hot key Detective](http://smallvoid.orgfree.com/?file=hotkeyd.zip "Hot key Detective 2.1") - Shows you the assigned hotkeys.  
 Related [WinKey](http://www.pcworld.com/downloads/file_description/0,fid,5506,00.asp)  
 Related [AutoHotkey](http://www.autohotkey.com/) - Any key-combination can become a hotkey.  
  
 More Info [MS KB134552](http://support.microsoft.com/kb/134552 "Shortcut Key for Shortcut Does Not Work [Q134552]")  
 More Info [MS KB142898](http://support.microsoft.com/kb/142898 "How to Assign a Shortcut Key to a Start Menu Item [Q142898]")  
 More Info [MS KB182366](http://support.microsoft.com/kb/182366 "Cannot Assign a Deleted Shortcut Key to a Different Shortcut [Q182366]")  
 More Info [MS KB192804](http://support.microsoft.com/kb/192804 "Desktop Shortcut Key Cannot Be Reassigned if Shortcut Is Deleted [Q192804]")  
 More Info [MS KB226098](http://support.microsoft.com/kb/226098 "Icons on the Quick Launch Toolbar Do Not Respond to Shortcut Key [Q226098]")  
 More Info [MS KB310417](http://support.microsoft.com/kb/310417 "HOW TO: Create a Keyboard Shortcut for a Program in Windows XP [Q310417]")  
  
 Microsoft Windows also provides some builtin shortcut keys to access different options within Windows. One can disable the Windows-key short cuts, in case you want to define your own new combined shortcuts (It will not disable the Windows-key itself):
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
 >  NoWinKeys = 1 (Default = 0)

 More Info [MS KB126449](http://support.microsoft.com/kb/126449 "Keyboard Shortcuts for Windows [Q126449]") (Keyboard shortcuts in Windows)  
 More Info [MS KB301583](http://support.microsoft.com/kb/301583 "A List of the Keyboard Shortcuts That Are Available in Windows XP [Q301583]") (Keyboard shortcuts in Windows XP)  
  
 Note Windows Vista includes a new keyboard shortcut ability, so one can use the combination Windows-key + number (1-9), and it will launch the shortcut in the Quick Launch bar that correspond to the number. More Info [Windows Vista - Keyboard shortcuts](http://windowshelp.microsoft.com/Windows/en-US/Help/2503b91d-d780-4c80-8f08-2f48878dc5661033.mspx).