---
title: 'Extend Folder Options to include your own tweaks'
date: '2003-08-10T23:27:42+02:00'
status: publish
permalink: /article/windows-folder-options.html
author: Snakefoot
excerpt: 'Folder Options can be extended to easily configure other settings in Windows.'
type: post
id: 286
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - folder-options
    - windows-explorer
post_format: []
tags:
    - 'folder-options,windows-explorer'
---
One can configure several options here:

- Win9x/Me/WinNT4: Open My Computer -&gt; View-menu -&gt; Folder Options...-item -&gt; View-tab
- Win2k/XP: Open My Computer -&gt; Tools-menu -&gt; Folder Options...-item -&gt; View-tab
 
 It is possible to add your own tweaks to these options, and allowing one to create a cheap tweaking tool, by applying a registry file that modifies the following registry key:
 > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced\]

 To add a new tweak item "IconCache" using Radio-Buttons:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\**IconCache**\]  
>  Text = "Icon Cache Size"  
>  Type = "group"  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\IconCache \\**Max**\]  
> **Text = "4096 Icons"**  
> **CheckedValue = dword:00001000** (Registry type and value)  
>  DefaultValue = dword:00000200 (Registry type and default value)  
>  ValueName = "Max Cached Icons" (Registry valuename)  
>  RegPath = "Software\\Microsoft\\Windows\\CurrentVersion\\Explorer" (Registry Path)  
>  HKeyRoot = dword:80000002 (HKEY\_LOCAL\_MACHINE section)  
>  Type = "radio"  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\IconCache \\**Large**\]  
> **Text = "2048 Icons"**  
> **CheckedValue = dword:00000800**  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\IconCache \\**Normal**\]  
> **Text = "512 Icons"**  
> **CheckedValue = dword:00000200**  
>   
>  Have cheated a little, as one have to copy the non-bold registry values from **Max**-section to **Large** and **Normal** section.

 To create a new tweak item "PaintDesktopVersion" using a Check-box:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\**Visual**\]  
>  Text = "Visual Options"  
>  Type = "group"  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\Visual \\**PaintDesktopVer**\]  
>  Text = "Show Version on Desktop"  
>  CheckedValue = dword:00000001  
>  UncheckedValue = dword:00000000  
>  DefaultValue = dword:00000000  
>  Type = "Checkbox"  
>  ValueName = "PaintDesktopVersion"  
>  RegPath = "Control Panel\\Desktop"  
>  HKeyRoot = dword:80000001 (HKEY\_CURRENT\_USER section)

 Note HKeyRoot specifies what section of the registry the RegPath applies:
- HKEY\_CLASSES\_ROOT 0X80000000
- HKEY\_CURRENT\_USER 0X80000001
- HKEY\_LOCAL\_MACHINE 0X80000002
 
 Note one can change the icon for a group by setting the "BitMap" value:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\**IconCache**\]  
>  Bitmap = "shell32.dll,4"

 Note one can change the "What This"-message (Right click an option to see):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\explorer \\Advanced \\**IconCache**\]  
>  HelpID = "update.hlp#51140"

 Related [Change Internet Options to include your own tweaks](/article/internet-explorer-options.html)  
  
 Credits [TechTrax](http://pubs.logicalexpressions.com/Pub0009/)