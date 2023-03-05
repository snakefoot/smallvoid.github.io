---
title: 'Rebuild icon cache to fix incorrectly displayed icons'
date: '2003-07-04T23:05:45+02:00'
status: publish
permalink: /article/windows-icon-cache.html
author: Snakefoot
excerpt: 'The icon cache can become corrupted and lead to icons being garbled.'
type: post
id: 285
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - icon-cache
    - icons
post_format: []
tags:
    - 'icon-cache,icons'
---
The icons used in Windows are saved in an icon cache, which has been invented to optimize the display of icons, so it doesn't have to open every exe-/dll-files and scan for icon images all the time.  
  
 This caching can become corrupted and lead to garbled/fuzzy/wrong icons:

- An icon are changed to a different random icon
- Several icons are drawn on top of each other
- An icon becomes all black
 
 There are different solutions that **might** help:
- Restarting the computer will solve the problem for most people
- Recreate the Icon-Cache by changing icon size (Another way is to **Rebuild Icons** in Tweak UI): 
  1. Open **Control Panel** and double click **Display**-applet
  2. Select **Appearance**-tab and in **Item**-dropdown select **Icon**
  3. Increase **Size** and press **Apply**-button
  4. Decrease **Size** back to old value and press **Apply**-button
  5. Press **Ok**-button
- Increase the limitation for the iconcache with this STRING value:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
  >  Max Cached Icons = "2048" (Range = "100"-"4096", Default = "512")
- Recreate the Icon-Cache file by deleting it 
  1. Delete the hidden file ShellIconCache (Win9x/NT4/2k):
     > C:\\Windows\\**ShellIconCache** or C:\\Winnt\\**ShellIconCache**
      
     Note in WinXP each user has their own file that is called Iconcache.db:
     > C:\\Documents and Settings\\Your User Name\\Local Settings\\Application Data\\**Iconcache.db**
      
     Note in Vista each user has their own file that is called Iconcache.db:
     > %USERPROFILE%\\AppData\\Local\\**Iconcache.db**
  2. Close down all explorer.exe processes using the Task Manager (Or else it will create a faulty file during logoff/restart)
  3. Use the Task Manager (CTRL+SHIFT+ESC) to launch the explorer.exe again (Or press CTRL+ALT+DEL to perform a restart/logoff)
  4. When the Windows Explorer (explorer.exe) starts again, it will recreate a correct Icon-Cache file
- Uninstall Tweak UI (If installed) using the Add/Remove applet in the Control Panel.  
    
   To uninstall by command line (WinNT+):
   > rundll32.exe syssetup.dll,SetupInfObjectInstallAction DefaultUninstall 4 %Windir%\\Inf\\Tweakui.Inf
  
   To uninstall by command line (Win9x):
   > rundll.exe setupx.dll,InstallHinfSection DefaultUninstall 4 C:\\Windows\\Inf\\Tweakui.Inf
 
 More Info [MS KB132668](http://support.microsoft.com/kb/132668 "Icons Randomly Change to Different Icons [Q132668]")  
 More Info [MS KB133733](http://support.microsoft.com/kb/133733 "Icons Displayed Incorrectly in Control Panel [Q133733]")  
 More Info [MS KB146213](http://support.microsoft.com/kb/146213 "Windows Explorer and Desktop Icons Appear Distorted [Q146213]")  
 More Info [MS KB199152](http://support.microsoft.com/kb/199152 "Desktop Icons Do Not Display Correctly in Windows NT 4.0 [Q199152]")  
 More Info [MS KB216165](http://support.microsoft.com/kb/216165 "Changes to Desktop Objects Are Not Displayed Properly [Q216165]")  