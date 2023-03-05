---
title: 'Modify the Windows registry with registry files'
date: '2001-01-01T12:44:00+01:00'
status: publish
permalink: /article/windows-update-registry.html
author: Snakefoot
excerpt: 'How to add and remove registry entries from the Windows registry using .reg files'
type: post
id: 241
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - regedit
    - registry
post_format: []
tags:
    - 'registry,regedit'
---
The Registry Editor (Regedit) in Windows is by default associated with registry files having the ".reg" file extension. And when double-clicking such a .reg file, then the registry editor will apply the registry entries specified in the .reg file.  
  
 The .reg file is just a standard text file, which can be edited with a text editor like Notepad. The syntax in the .reg file allows one to add, update and remove registry entries from the Windows registry. When using the Registry Editor to export a registry value, then it will save the registry values in a .reg file, and then one can edit the .reg file or import it on a another computer.  
  
 To add / change a value in the registry:

> REGEDIT4  
>   
>  \[HKEY\_CURRENT\_USER\\Environment\]  
>  "MyEnvironmentVariable" = "Hello"

 To delete a value in the registry (Notice the "-"):
> REGEDIT4  
>   
>  \[HKEY\_CURRENT\_USER\\Environment\]  
>  -"MyEnvironmentVariable"

 To delete key with all its sub-keys (Notice the "-"):
> REGEDIT4  
>   
>  \[-HKEY\_CURRENT\_USER\\Environment\]

 Note it is possible to apply a registry file silently without user interaction, by using this command line parameter:
 > Regedit.exe /S &lt;filename&gt;.reg

 Note another option for modifying the registry from the command line is to use the utility Reg.exe (Can be found in Ressource Kits). Run Reg.exe /? to see how it is used.