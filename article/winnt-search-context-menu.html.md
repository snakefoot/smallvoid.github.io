---
title: 'Restore search context menu option in Vista SP1+'
date: '2008-10-02T02:43:02+02:00'
status: publish
permalink: /article/winnt-search-context-menu.html
author: Snakefoot
excerpt: 'The "Search..." context menu option has been removed with Windows Vista Service Pack 1'
type: post
id: 773
category:
    - Desktop
tag:
    - context-menu
    - file-search
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,file-search,context-menu'
---
Windows Explorer gives a "Search..." option when right-clicking a drive-letter or a folder. This option has been removed with Windows Vista SP1.  
  
 The rumor says this has happened to prevent the Microsoft Desktop Search from being too well integrated compared to third party search engines. More Info [Microsoft to address Google search complaint in Vista SP1](http://blogs.zdnet.com/microsoft/?p=524)  
  
 The "Search..." context-menu items has been hidden by registering them as being legacy verbs for backward compatibility. More Info [Verbs and File Associations](http://msdn.microsoft.com/en-us/library/cc144175.aspx#legacydisable)  
  
 Restore the "Search..." option by removing the registry string value **LegacyDisable** from these locations:

- \[HKEY\_CLASSES\_ROOT \\Directory \\shell \\find\]
- \[HKEY\_CLASSES\_ROOT \\Drive \\shell \\find\]
 
 Credits [VistaX64.com](http://www.vistax64.com/tutorials/134065-search-context-menu-item-restore-after-vista-sp1.html "Search Context Menu Item - Restore After Vista SP1")