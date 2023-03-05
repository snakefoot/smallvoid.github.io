---
title: 'Extend context menu with "Open with..." for all files'
date: '2000-01-01T23:43:45+01:00'
status: publish
permalink: /article/win9x-open-with-all-files.html
author: Snakefoot
excerpt: 'Configure the context-menu when right-clicking any file to show "Open with..."'
type: post
id: 125
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - context-menu
    - open-with
    - openas
    - windows-explorer
post_format: []
tags:
    - 'context-menu,windows-explorer,openas,open-with'
---
When wanting to open a file with a different program than the one assigned by default, then one have to hold down the SHIFT-key while right clicking to access the "Open with..." option.  
  
 If frequently opening files with other programs than the default one then one can modify the registry so the "Open with..." option is available at right clicking without needing to hold the SHIFT-key down:

> \[HKEY\_CLASSES\_ROOT \\\* \\shell \\openas \\command\]  
>  @="Rundll32.exe Shell32.dll,OpenAs\_RunDLL %1"

 Note that you might have to delete this key unless you want two "Open With.." when right-clicking a file with unknown type:
 > \[HKEY\_CLASSES\_ROOT \\Unknown \\shell **\\openas**\]

 Related [Configure file types to include your own useful actions](/article/explorer-context-menu.html)  
 Related [Open files of an unknown type with notepad](/article/win9x-unknown-file-notepad.html)  