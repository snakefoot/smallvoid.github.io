---
title: 'Create shortcut to &quot;Run...&quot; in the Start Menu'
date: '2006-01-31T00:46:39+01:00'
status: publish
permalink: /article/windows-start-menu-run.html
author: Snakefoot
excerpt: 'The Run... option in the Start Menu can be launched using a shortcut.'
type: post
id: 307
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - start-menu
post_format: []
tags:
    - start-menu
---
It is possible to open the "Run..." dialog by using the [keyboard shortcut](/article/windows-keyboard-shortcuts.html) (Windows-Key+R).  
 It is also possible to create a normal shortcut with an icon that points to the "Run..." dialog.

1. Create a text file named **Run.js**, which contains the following line:
   > (new ActiveXObject("Shell.Application")).FileRun();
2. Right-click **Run.js** and select "Create shortcut"
3. Right-click the created shortcut and select "Properties"
4. Add "**WScript.exe** " (Without quotes) to the beginning of "Target:"
5. If wanting to change the icon of the shortcut press "Change Icon" else press "Ok"
 
 Note the same technique can be used to launch the Search dialog:
 > (new ActiveXObject("Shell.Application")).FindFiles();

 Note if using Windows XP, then one can also create the icon by dragging the "Run..." icon from the Start Menu to the Desktop (Doesn't work in Classic Mode).  
  
 Credits [The Old New Thing](http://blogs.msdn.com/oldnewthing/)