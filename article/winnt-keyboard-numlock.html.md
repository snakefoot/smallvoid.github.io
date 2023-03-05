---
title: 'Control the keyboard numlock state at startup'
date: '2004-03-06T20:22:58+01:00'
status: publish
permalink: /article/winnt-keyboard-numlock.html
author: Snakefoot
excerpt: 'Configure whether the num-lock, caps-lock or scroll-lock keys should be turned on or off at startup.'
type: post
id: 387
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - keyboard
    - numlock
    - windows-login
post_format: []
tags:
    - 'numlock,keyboard,windows-login'
---
It is possible to configure whether Numlock should be enabled after logging in. The activation is controlled by setting this registry STRING value:

> \[HKEY\_CURRENT\_USER \\ Control Panel \\ Keyboard\]  
>  InitialKeyboardIndicators = "0"  
>   
>  "0" - All Keys off  
>  "1" - Caps Lock on  
>  "2" - Num Lock on  
>  "4" - Scroll Lock on  
>   
>  For multiple keys, add their values:  
>  "3" - Caps Lock and Num Lock on  
>  "5" - Caps Lock and Scroll Lock on  
>  "6" - Num Lock and Scroll Lock on  
>  "7" - Caps Lock, Num Lock, and Scroll Lock on  
>   
>  "2147483648" - Honor the motherboard BIOS setting (Vista only)  
>   
>  More info [MS KB101898](http://support.microsoft.com/kb/101898 "Keyboard Light Indicator Disabled when User Logs On [Q101898]")

 Note it is also possible to configure Numlock state at startup before actually performing the login at the Welcome Screen, by setting the value for the default user:
> \[HKEY\_USERS \\.Default \\Control Panel \\Keyboard\]  
>  InitialKeyboardIndicators = "0"  
>   
>  More info [MS KB154529](http://support.microsoft.com/kb/154529 "How to Enable the NUM LOCK Key for the Logon Screen [Q154529]") (Merged with MS KB315468)

 Note if numlock is turned off before Windows has reached the login screen, then it might be caused by numlock not being activated in the motherboard BIOS.  
  
 Credits [OneComputerGuy.com](http://www.onecomputerguy.com/)