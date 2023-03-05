---
title: 'Disable hotkey activation of sticky keys'
date: '2004-05-10T22:36:03+02:00'
status: publish
permalink: /article/winnt-sticky-keys.html
author: Snakefoot
excerpt: 'Sticky keys is an accessibility features, that can be activated with a shortcut key (often by accident when inside a game).'
type: post
id: 400
category:
    - Tips
    - Tips
    - Tips
tag:
    - accessibility-tools
    - shortcut-keys
    - sticky-keys
post_format: []
tags:
    - 'sticky-keys,accessibility-tools,shortcut-keys'
---
It is possible to control the computer even if not having both hands available by using the accessibility features. Sticky keys is one part of this collection of features and allows Windows to help to hold down several keys on the keyboard. By pressing SHIFT several (5) times in a row then the Sticky Keys configuration is presented. One cannot remove/disable sticky keys completely, but only disable the hotkey activation of sticky keys.  
  
 The sticky keys feature is not used by many, but for those who play games and have assigned SHIFT or CTRL for a certain action in the game might get annoyed by the Sticky Keys configuration screen. (Especially if having uninstalled the accessibility options so one cannot turn off the activation of Sticky Keys via the user interface).  
  
 Change this registry key to disable the hotkey activation (FKF\_HOTKEYACTIVE) of sticky keys:

> \[HKEY\_CURRENT\_USER \\Control Panel \\Accessibility \\StickyKeys\]  
>  Flags = "506" (Default = "510")  
>   
>  More Info [MSDN: Accessibility StickyKeys](http://msdn.microsoft.com/library/en-us/msaa/access_1alu.asp)

 Note one can completely disable accessibility options by renaming/deleting the registry-node **Accessibility** (Shown above).  
  
 Related [Using Sticky Keys activation to reset Administrator password](/article/winnt-reset-password.html).  