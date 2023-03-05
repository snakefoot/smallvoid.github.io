---
title: 'Utilities to configure file associations in Windows Explorer'
date: '2005-11-09T01:02:16+01:00'
status: publish
permalink: /article/utility-explorer-context-menu.html
author: Snakefoot
excerpt: 'Utilities that makes it easier to modify the Windows Explorer context menu for the different filetypes.'
type: post
id: 119
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - context-menu
    - file-association
    - file-type
    - windows-explorer
post_format: []
tags:
    - 'context-menu,file-association,file-type,windows-explorer'
---
Windows Explorer already has an interface for customizing the file associations for the different file types. See [Customize the right-click menu in Windows Explorer](/article/explorer-context-menu.html).  
 The default Windows Explorer file type editor is rather limited (especially in Vista/Win7 where you can't change the behavior of the edit or play context menu options). Instead one can consider a 3rd party file association editor, that allows editing of even special file types like All Files, Unknown Files, Drives etc.

- [FileTypesMan](http://www.nirsoft.net/utils/file_types_manager.html) - File Types Manager for Windows
- [File Type Manager](http://frank.neatstep.com/node/1)
- [Default Programs Editor](http://defaultprogramseditor.com/) - Requires the .NET Framework
- [Fast Explorer](http://thesoftpro.tripod.com/)
- [ShellExView](http://www.nirsoft.net/utils/shexview.html) - Shell Extensions Manager. Shell extensions are dlls loaded into Windows Explorer, and can modify the context menu.

##### Modify the context menu with manual registry editing

 If everything fails, then one can also adventure directly into the registry database to fix file-type association:
1. Open the Registry Editor (regedit.exe) and go the registry-key matching the file-extension (ex. **.txt**):
 > \[HKEY\_CLASSES\_ROOT \\.txt\]
  
   The **(Default)** value below this registry-key will specify a logical name (ex. **txtfile**) or an application name.  
    
   The use of a logical name is smart when multiple file-extensions (text and txt) should have the same context menu, then it is just a matter of making them point to the same logical name.
2. Browse to the registry-key specified with the logical name (ex. **txtfile**):
  > \[HKEY\_CLASSES\_ROOT \\txtfile\]
 Below this registry key there is a **shell** folder, and all available commands for this logical name are listed there. One can then add, modify or remove commands from that list.  
  
 More Info [MSDN - Extending Shortcut Menus](http://msdn.microsoft.com/en-us/library/bb776820.aspx)