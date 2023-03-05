---
title: 'Install support for zip files as compressed folders'
date: '2004-10-10T17:59:20+02:00'
status: publish
permalink: /article/windows-zip-folder.html
author: Snakefoot
excerpt: 'Extension for the Windows Explorer so zip files can be opened like a normal directory.'
type: post
id: 363
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - archive
    - compress
    - compressed-folders
    - extract
    - zip
post_format: []
tags:
    - 'zip,extract,compress,compressed-folders,archive'
---
[Compressed Folders](/article/windows-compressed-folders.html) is a shell extension for Windows Explorer that allows ZIP and CAB files to be opened like ordinary file folders.  
  
 To install zip file support in Windows 95, 98 or 2000:
1. Download <a href=""></a> (Contains 3 DLL extracted from [MS KB329048](http://support.microsoft.com/kb/329048 "MS02-054: Unchecked Buffer in File Decompression Functions May Allow Attacker to Run Code [Q329048]")) and extract the files to the following location: 
  - If using Windows 95/98 place them in **C:\\Windows\\System**
  - If using Windows 2000 place them in **C:\\Winnt\\System32**
2. Press **Start**-button and **Run...** this command:
   > Regsvr32 zipfldr.dll
 
 To uninstall / disable compressed folders run this command:
 > Regsvr32 /u zipfldr.dll

 Related [Install support for cab files as compressed folders](/article/win95-power-toys.html)