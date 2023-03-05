---
title: 'Open files of an unknown type with notepad'
date: '2000-01-01T00:17:17+01:00'
status: publish
permalink: /article/win9x-unknown-file-notepad.html
author: Snakefoot
excerpt: 'Configure the default behavior to use notepad, when opening a file with unknown type.'
type: post
id: 115
category:
    - Desktop
    - Desktop
tag:
    - notepad
    - open-with
post_format: []
tags:
    - 'open-with,notepad'
---
By default when double clicking a file with an unknown filetype, then it starts with "Open with..". It is possible to change the default behavior to instead open the Notepad. One can still access the "Open with..." option by holding down the Shift-key and right-clicking the file.

> REGEDIT4  
>   
>  \[HKEY\_CLASSES\_ROOT\\Unknown\\shell\\open\]  
>  @=""  
>   
>  \[HKEY\_CLASSES\_ROOT\\Unknown\\shell\\open\\command\]  
>  @="NOTEPAD.EXE \\"%1\\""

 Note instead of modifying the registry to make notepad default viewer for unknown file types, then one could use the [Send To](/article/sendto-shortcut.html)-folder for easy access to the favorite file-viewers.  
  
 Related [Configure file types to include your own useful actions](/article/explorer-context-menu.html)  
 Related [Extend context menu with "Open with" for all files](/article/win9x-open-with-all-files.html)  