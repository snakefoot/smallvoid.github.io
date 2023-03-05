---
title: 'Windows Explorer command line switches'
date: '2000-01-01T22:25:52+01:00'
status: publish
permalink: /article/windows-explorer.html
author: Snakefoot
excerpt: 'Windows Explorer allows one to specify what folder to display when launched.'
type: post
id: 273
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Tips
    - Tips
    - Tips
tag:
    - command-line-switches
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,command-line-switches'
---
> explorer.exe \[/n\]\[,/e\]\[,/root,object\]\[\[,/select\],subobject\]

- **/n** - always open a new window (even if the specified folder is already open)
- **/e** - uses windows explorer view(Tree view)
- **/root,object** - Specify the object in the normal namespace that will be used as the root of this Windows Explorer Folder
- **subobject** - Specify the folder to receive the initial focus unless /select is used
- **/select** - Specifies that the parent folder is opened and the specified object(program) is selected.
 
 Remember the "," between command line switches.  
  
 Examples of different commands:
- Opens My Computer with tree-view (With Drive-Letter A: selected):
  > Explorer.exe /e,/select,A:
- Opens C-Drive with tree-view:
  > Explorer.exe /e,/root,c:\\
- Opens Desktop with tree-view:
  > Explorer.exe /e,/select,
- Opens [special folder](/article/windows-special-folders.html):
  > explorer.exe /e,::{20D04FE0-3AEA-1069-A2D8-08002B30309D}
 
 More Info [MS KB130510](http://support.microsoft.com/kb/130510 "Command-Line Switches for Windows Explorer [Q130510]")  
 More Info [MS KB307856](http://support.microsoft.com/kb/307856 "HOW TO: Customize the Windows Explorer Views in Windows XP [Q307856]")  
 More Info [MS KB314853](http://support.microsoft.com/kb/314853 "Explorer.exe Command-Line Options for Windows XP [Q314853]")  