---
title: 'Configure zip and cab files as compressed folders'
date: '2001-10-01T19:36:47+02:00'
status: publish
permalink: /article/windows-compressed-folders.html
author: Snakefoot
excerpt: 'Open zip and cab files in Windows Explorer like they were normal directory with files.'
type: post
id: 402
category:
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
    - Desktop
tag:
    - archive
    - cab
    - compress
    - compressed-folders
    - extract
    - zip
post_format: []
tags:
    - 'compress,extract,zip,cab,archive,compressed-folders'
---
Compressed folders is a shell extension for Windows Explorer, which makes it possible to open compressed files like they were ordinary folders in Windows Explorer. Currently zip- and cab-archives are capable of being opened like a compressed folder.

- Windows 95 / NT4 - Can by default not open archives as compressed folders. 
  - [Install support for zip files as compressed folders](/article/windows-zip-folder.html)
  - [Install support for cab files as compressed folders](/article/win95-power-toys.html)
- Windows 98 / 2000 - Supports cab files by default, but not zip files. 
  - [Install support for zip files as compressed folders](/article/windows-zip-folder.html)
- Windows Me / XP / 2003 - Supports cab and zip files by default.
 
 Windows XP / 2003 extends the functionality of compressed folders by allowing the file search to open and look through zip and cab archives. This can slow down the file search significantly, so if already using a different utility to handle compressed files, then one can consider to disable the compressed folders functionality.  
  
 To disable the compressed folder functionality use these commands (reboot after executing the commands):
 > regsvr32 /u cabview.dll  
 > regsvr32 /u zipfldr.dll

 To enable the compressed folder functionality again use these commands:
 > regsvr32 cabview.dll  
 > regsvr32 zipfldr.dll

 More info [MS KB197144](http://support.microsoft.com/kb/197144 "Cannot Use CabView Tool to View Contents of Cabinet Files [Q197144]")  
 More info [MS KB306531](http://support.microsoft.com/kb/306531 "HOW TO: Use Compressed (Zipped) Folders in Windows XP [Q306531]")  