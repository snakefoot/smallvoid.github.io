---
title: 'Open Command Prompt Here'
date: '2002-03-01T01:15:19+01:00'
status: publish
permalink: /article/winnt-open-command-prompt-here.html
author: Snakefoot
excerpt: 'Extend the right-click context-menu of a folder to open a command prompt.'
type: post
id: 121
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - 'Command Prompt'
    - context-menu
    - windows-explorer
post_format: []
tags:
    - 'context-menu,windows-explorer,command-prompt'
---
One can extend the context menu when right-clicking a folder in Windows Explorer, with the option to open a command prompt in that directory. Instead of just opening the command prompt and manually changing to the wanted directory.

- Windows Vista - Will display the option "Open Command Window Here" when right-clicking a folder, while holding down the SHIFT key (Part of the extended context menu options).
- Windows XP - Download the [WinXP Powertoy - Open Command Window Here](/article/winxp-power-toys.html).
- Other versions of Windows - Try using [WinXP Powertoy BETA2 - Open Command Window Here](http://smallvoid.orgfree.com/?file=cmdinstall.zip), which isn't locked to only work on Windows XP.

##### Manual add option using Windows Explorer

 To manually add the option through Windows Explorer interface:
1. Start "My Computer"
2. In the "My Computer" menu select "Tools" -&gt; "Folder Options..."
3. Select the fan "File Types"
4. Sort the registered file types by name by clicking the 2nd column
5. Find and select the file type "Folder"
6. Press the "Advanced" button, and a new window pops up
7. Press the "New..." button, and a new window pops up
8. Set the action to be:
   > Open Command Prompt Here
9. Set the application to be:
   > cmd.exe /k "cd %L"
  
   Note that the "%L" is used to show the long name of the directory. If you use "%1" then it will use the 8.3 format.
10. Press Ok to save the newly added entry
 
 Related [Configure file types to include your own useful actions](/article/explorer-context-menu.html)
 
##### Manual add option using Registry Editor

 Note one can also extend the context menu by applying the following registry settings. More Info [MS KB320148](http://support.microsoft.com/kb/320148 "How to start a command prompt in a folder in Windows Server 2003, Windows XP, and Windows 2000"):
> REGEDIT4  
>   
>  \[HKEY\_CLASSES\_ROOT\\Directory\\shell\\cmd\]  
>  @="Open Command Window Here"  
>   
>  \[HKEY\_CLASSES\_ROOT\\Directory\\shell\\cmd\\command\]  
>  @="cmd.exe /k \\"cd %L\\""  
>   
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shell\\cmd\]  
>  @="Open Command Window Here"  
>   
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shell\\cmd\\command\]  
>  @="cmd.exe /k \\"cd %L\\""

 Note if not running as administrator by default, and want to open a command prompt session with administrator rights, then it can be done by adding a [RunAs](/article/winnt-services-seclogon.html) option for the directory filetype (Useful if using Windows Vista):
> REGEDIT4  
>   
>  \[HKEY\_CLASSES\_ROOT\\Directory\\shell\\runas\]  
>  @="Open Command Window Here (Administrator)"  
>   
>  \[HKEY\_CLASSES\_ROOT\\Directory\\shell\\runas\\command\]  
>  @="cmd.exe /k \\"cd %L\\""  
>   
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shell\\runas\]  
>  @="Open Command Window Here (Administrator)"  
>   
>  \[HKEY\_CLASSES\_ROOT\\Drive\\shell\\runas\\command\]  
>  @="cmd.exe /k \\"cd %L\\""