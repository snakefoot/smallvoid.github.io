---
title: 'Starting Internet Explorer in full screen'
date: '2003-08-26T00:19:53+02:00'
status: publish
permalink: /article/ie-full-screen.html
author: Snakefoot
excerpt: 'Different ways for starting Internet Explorer in full screen mode.'
type: post
id: 318
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - full-screen
post_format: []
tags:
    - full-screen
---
Internet Explorer (IE) remembers its position and size when being closed down. In case one wants to change the remembered position to full screen, do the following:

1. Close down all instances of Internet Explorer (Use the Task Manager to close down all iexplore.exe)
2. Start a new Internet Explorer 
  - If experiencing that clicking a hyperlink in another application opens Internet Explorer with a wrong size, then start Internet Explorer by clicking the hyperlink.
3. Resize the Internet Explorer window so it fills the whole desktop, then wait 5 seconds. 
  - To quickly resize the IE window to fill the entire desktop, just close/minimize all other windows except a single IE window and then right click in the taskbar and either select "Tile windows horizontally" or "Tile windows vertically".
4. Close the Internet Explorer by holding down CTRL while going to the **File** and selecting **Close** (Don't use the \[x\] to close)
5. When opening Internet Explorer again, then the window should have the expected size 
  - One might have to repeat these steps a few times to make Internet Explorer remember properly.
 
 There are also alternative ways to configure it for full screen:
 - Change shortcut properties for IE to start Maximized (Toolbars in several lines). 
  1. Right click the short cut used to start IE and select **Properties**
  2. Change **Run**-dropdown from **Normal Window** to **Maximized**
  3. Press **Ok**-button
   
 Note links that opens a new IE instance will not be maximized.
 - Changing registry key for IE to startup in full screen like when have pressed F11 (Toolbars in a single line). > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Main\]  
  >  Fullscreen = "yes" (Default = "no")
  
   Note links that opens a new IE instance will not be full screen.  
    
   Note one can make the taskbar appear using CTRL+ESC, Windows-Key, or just move mouse to bottom of screen.  
    
   Noticed that when playing with this value in the registry it reverted back to "no" when closing an IE in normal mode, but after setting it a few times it kept the value.  
    
   More Info [MS KB197029](http://support.microsoft.com/kb/197029 "How to Configure Internet Explorer 5 for Full Screen Mode [Q197029]")
- Change shortcut properties for IE to start in Kiosk mode (Toolbars not allowed) 
  1. Right click the short cut used to start IE and select **Properties**
  2. Change **Target**-line by appending a **-k** to the end of the command
  3. Press **Ok**-button
   
   Note links that opens a new IE instance will not be full screen.  
    
   Note one can use ALT+F4 to close down the Internet Explorer and CTRL+ESC or Windows-key to make the taskbar appear.  
    
   More Info [MS KB154780](http://support.microsoft.com/kb/154780 "How to Use Kiosk Mode in Microsoft Internet Explorer [Q154780]")
- Internet Explorer saves its position in this registry key, one can create a batch file that [sets this key](/article/windows-update-registry.html) and then starts IE (Use start /wait):

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Main\]  
>  Window\_Placement=