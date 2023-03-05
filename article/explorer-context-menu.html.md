---
title: 'Customize the right-click menu in Windows Explorer'
date: '2000-01-01T00:31:42+01:00'
status: publish
permalink: /article/explorer-context-menu.html
author: Snakefoot
excerpt: 'Adding own actions to the context menu when right clicking a file in Windows Explorer.'
type: post
id: 116
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
    - drive-mount
    - file-association
    - file-type
    - windows-explorer
post_format: []
tags:
    - 'file-type,file-association,drive-mount,context-menu,windows-explorer'
---
Windows creates by default several actions for the different file-types (JPG,TXT,HTM,etc.) that it knows. These actions are shown in the context-menu when right clicking a file (or folder), and depending of the file-type a different set of actions are available.  
  
 It is possible to add your own useful actions to the context-menu, when right clicking a file (or folder).

##### Customize the context menu for a file type in WinXP/2k/Me

1. Open My Computer -&gt; Tools-menu -&gt; Folder Options...-item -&gt; File Types-tab
2. Find the wanted File Type (Ex. .DOC) and press "Advanced", and it will show the actions currently associated with the file-type
3. Press "New" to add another action to be shown when right click that file-type

##### Customize the context menu for a file type in Win9x/WinNT4

1. Open My Computer -&gt; View-menu -&gt; Folder Options...-item -&gt; File Types-tab
2. Find the wanted File Type (Ex. .DOC) and press "Edit", and it will show the actions currently associated with the file-type
3. Press "New" to add another action to be shown when right click that file-type

##### Ideas for adding new actions

- **Unzip all files inside a Folder**  
   Add "Unzip All" to the "Folder"-filetype, which decompresses all zip-files within the folder: 
  - Using [7Zip](http://www.7-zip.org/) command line tool:
  > C:\\7Zip\\7z x "%1\\\*.zip" -o"%1\\UNZIPPED\\" -r
  - Using [WinZip](http://www.winzip.com/downcl.htm) command line tool (WZunzip):
  > C:\\WinZip\\Wzunzip.exe -d "%1\\\*.zip" "%1\\UNZIPPED\\"
  - Using [Pkware](http://www.pkware.com/) command line tool (Pkunzip):
  > C:\\PKZip\\Pkunzip.exe -d %1\\\*.ZIP -o %1\\UNZIPPED\\
- **Mount ISO image**  
   Add "Mount Image" to the "ISO"-filetype, which mounts the image using [Daemon Tools](http://www.daemon-tools.cc/)> C:\\D-Tools\\Daemon.exe -mount 0,"%1"
- **Open Command Prompt here**  
   Add "Command Prompt Here" to the "Folder"-filetype: 
  - [Open Command Prompt Here](/article/win9x-open-command-prompt-here.html) (Win9x)
  - [Open Command Prompt Here](/article/winnt-open-command-prompt-here.html) (WinNT4/Win2k/WinXP)
 
 Related [Utilities to modify the Explorer context menu](/article/utility-explorer-context-menu.html)  
 Related [Extend context menu with Move To and Copy To options](/article/context-move-copy-to.html)  
 Related [Extend context menu with Copy Path](/article/windows-copy-path.html)  