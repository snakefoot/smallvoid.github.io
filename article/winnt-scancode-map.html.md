---
title: 'Configure the keyboard mapping using scancode map'
date: '2001-04-17T18:24:03+02:00'
status: publish
permalink: /article/winnt-scancode-map.html
author: Snakefoot
excerpt: 'How to use the scancode map to modify the keyboard layout and disable the Windows-key.'
type: post
id: 380
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - keyboard
    - scancode-map
    - shortcut-keys
    - windows-key
post_format: []
tags:
    - 'scancode-map,shortcut-keys,windows-key,keyboard'
---
It is possible to change the behavior of the different keys on the keyboard by changing the scancode map. This can be used to disable the Windows-key so one is not thrown out of your favorite game, when by accident have pressed the wrong key.  
  
 The change the scancode map, so the Windows-key is disabled add/update this binary value:

> REGEDIT4  
>   
>  \[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Keyboard Layout\]  
>  "Scancode Map"=hex:00,00,00,00,00,00,00,00,03,00,00,00,00,00,5b,e0,00,00,5c,e0,\\  
>  00,00,00,00

 For those who wants to know the meaning of the above values here goes:  
  
<table border="1"><tr><td>00,00,00,00</td><td>Header: Version. Set to all zeroes.</td></tr><tr><td>00,00,00,00</td><td>Header: Flags. Set to all zeroes.</td></tr><tr><td>03,00,00,00</td><td>3 entries in the map (including null entry).</td></tr><tr><td>00,00,5b,e0</td><td>Left Windows Key (0xe05b) -&gt; Disable (0x00).</td></tr><tr><td>00,00,5c,e0</td><td>Right Windows Key (0xe05c) -&gt; Disable (0x00).</td></tr><tr><td>00,00,00,00</td><td>Null entry.</td></tr></table>

  
 To also disable the Shutdown key, one would extend the Scancode Map, so it has 4 entries where the fourth entry becomes ACPI Power Key (0xe0f6) -&gt; Disable (0x00):
> REGEDIT4  
>   
>  \[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Keyboard Layout\]  
>  "Scancode Map"=hex:00,00,00,00,00,00,00,00,04,00,00,00,00,00,5b,e0,00,00,5c,e0,\\  
>  00,00,f6,e0,00,00,00,00

 Note it is also possible to map the the Shutdown keyboard key to become Sleep shortcut by going to Control Panel -&gt; Power Options -&gt; Advanced Tab.  
  
 More Info [KeyTweak by Travis Krumsick](http://webpages.charter.net/krumsick/)  
 More Info [SharpKeys by RandyRants.com](http://www.randyrants.com/sharpkeys/)  
 More Info [Microsoft Keyboard Layout Creator (MSKLC)](http://www.microsoft.com/downloads/details.aspx?FamilyID=fb7b3dcd-d4c1-4943-9c74-d8df57ef19d7)  
 More Info [Scan Code Mapper for Windows](http://www.microsoft.com/whdc/archive/w2kscan-map.mspx)  
 More Info [MS KB181348](http://support.microsoft.com/kb/181348 "Disabling the Windows Key on Microsoft Natural Keyboard [Q181348]")  
 More Info [MS KB216893](http://support.microsoft.com/kb/216893 "How To Disable the Keyboard Windows Key [Q216893]")  
  
 Related [Using keyboard shortcuts/hotkeys to quickly access programs](/article/windows-keyboard-shortcuts.html)  
  
 Credits [Jason Tsang](http://jtsang.mvps.org/flock.html)