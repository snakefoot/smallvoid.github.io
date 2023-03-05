---
title: 'Extend context menu with Move To and Copy To options'
date: '2001-01-26T00:41:50+01:00'
status: publish
permalink: /article/context-move-copy-to.html
author: Snakefoot
excerpt: 'Add "Copy To Folder..." and "Move To Folder..." when right-clicking a file.'
type: post
id: 117
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - context-menu
    - file-copy
    - windows-explorer
post_format: []
tags:
    - 'context-menu,file-copy,windows-explorer'
---
In Windows Explorer one can select a file and then go to the **Edit**-menu and select **Copy To Folder...** or **Move To Folder...**. This allows one to copy/move the file without needing to open another Windows Explorer or leave the current directory.  
  
 One can add the **Copy To Folder...** and **Move To Folder...** to the toolbar of Windows Explorer by right-clicking a blank space and selecting customize. One can also add them to the context menu, when right-clicking a file or folder.

##### Copy To Folder

 Extend context menu with "Copy To Folder...":
 
> REGEDIT4  
>   
>  ;All Files  
>  \[HKEY\_CLASSES\_ROOT\\\*\\shellex\\ContextMenuHandlers\\Copy To\]  
>  @="{C2FBB630-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All Drives  
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shellex\\ContextMenuHandlers\\Copy To\]  
>  @="{C2FBB630-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All Files and Folders  
>  \[HKEY\_CLASSES\_ROOT\\AllFilesystemObjects\\shellex\\ContextMenuHandlers\\Copy To\]  
>  @="{C2FBB630-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All editable Files and Folders  
>  \[HKEY\_CLASSES\_ROOT\\AllFilesystemEditObjects\\shellex\\ContextMenuHandlers\\Copy To\]  
>  @="{C2FBB630-2971-11D1-A18C-00C04FD75D13}"

##### Move To Folder

 Extend context menu with "Move To Folder...":
 
> REGEDIT4  
>   
>  ;All Files  
>  \[HKEY\_CLASSES\_ROOT\\\*\\shellex\\ContextMenuHandlers\\Move To\]  
>  @="{C2FBB631-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All Drives  
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shellex\\ContextMenuHandlers\\Move To\]  
>  @="{C2FBB631-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All Files and Folders  
>  \[HKEY\_CLASSES\_ROOT\\AllFilesystemObjects\\shellex\\ContextMenuHandlers\\Move To\]  
>  @="{C2FBB631-2971-11D1-A18C-00C04FD75D13}"  
>   
>  ;All editable Files and Folders  
>  \[HKEY\_CLASSES\_ROOT\\AllFilesystemEditObjects\\shellex\\ContextMenuHandlers\\Move To\]  
>  @="{C2FBB631-2971-11D1-A18C-00C04FD75D13}"

 Note when adding these registry keys, then one might get the **Copy To Folder...** and **Move To Folder...** some weird places (Like when right-clicking Outlook Attachments) where these options will not work. More Info [The Old New Thing](http://blogs.msdn.com/oldnewthing/archive/2004/02/02/66160.aspx)  
  
 Note when adding these registry keys, then it might mess up the ability to select multiple files and select **Open** or **Print**, where it instead will request either **Copy To Folder...** or **Move To Folder...** for each file selected. To fix this issue run the following command in Windows 2000/XP:
 
 > regsvr32 /i shell32.dll

 Related [Send To X](/article/win95-power-toys.html) (Extends the SentTo-folder with "Send to any folder")  
  
 Credits [mdgx.com](http://www.mdgx.com/)