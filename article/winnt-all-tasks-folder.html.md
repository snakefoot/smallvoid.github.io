---
title: 'All Tasks can be accessed through a special Control Panel'
date: '2008-11-01T15:40:32+01:00'
status: publish
permalink: /article/winnt-all-tasks-folder.html
author: Snakefoot
excerpt: 'The All Tasks folder gives a quick overview of all the options available in the Control Panel.'
type: post
id: 779
category:
    - Tips
    - Tips
tag:
    - control-panel
    - windows-explorer
post_format: []
tags:
    - 'control-panel,windows-explorer'
---
It is possible to access a special folder, that will display all tasks available through the normal Control Panel.

> **NB** This tip is NOT compatible with Vista x64, but works fine on Vista 32 bit and Windows 7.  
>   
>  If having created the folder on the desktop and experience that Windows Explorer crashes on Vista x64, then one can open a command prompt and remove the folder with this command (Notice the quotes):  
>   
>  rd "All Tasks.{ED7BA470-8E54-465E-825C-99712043E01C}"

 There are different ways to access this advanced Control Panel:
- Launch this command through the Start-menu:
  > shell:::{ED7BA470-8E54-465E-825C-99712043E01C}
- Create a new folder on the Desktop with the following name:
  > All Tasks.{ED7BA470-8E54-465E-825C-99712043E01C}
 
 Related [Access special folders easily using the shell command](/article/winnt-shell-keyword.html)  
 Related [Create special folders where you want them](/article/windows-special-folders.html)  
  
 Credits [ItsMyWindows.com](http://www.itsmywindows.com/how-to-create-a-master-control-panel-for-windows-vista-and-explore-the-all-tasks)