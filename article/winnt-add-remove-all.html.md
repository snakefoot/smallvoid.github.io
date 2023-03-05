---
title: 'Display all components in the Control Panel Add/Remove applet'
date: '2001-04-02T20:17:39+02:00'
status: publish
permalink: /article/winnt-add-remove-all.html
author: Snakefoot
excerpt: 'Windows does not by default display all items that can be uninstalled in the Add / Remove applet.'
type: post
id: 386
category:
    - Tips
    - Tips
    - Tips
tag:
    - control-panel
    - free-disk-space
    - uninstall
post_format: []
tags:
    - 'uninstall,control-panel,free-disk-space'
---
There are some components in the Add/Remove applet in the Control Panel which are hidden in the different versions of Windows 2000/XP (Like the Games).  
  
 To unhide these components do the following :

1. Find the file SYSOC.INF which usually resides in C:\\WINNT\\INF
2. Make a backup of the file
3. Edit the file with a text editor like notepad
4. Remove every occurrence of "HIDE" (Use Replace...)
5. Save and exit and now the Add/Remove applet will show more options for the Windows Components
 
 Credits [rojakpot.com](http://www.rojakpot.com/)