---
title: 'File and directory completion with keyboard shortcut'
date: '2001-01-01T23:51:58+01:00'
status: publish
permalink: /article/winnt-file-directory-completion.html
author: Snakefoot
excerpt: 'How to assign keyboard shortcut to file and directory completion in command prompt.'
type: post
id: 4
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - keyboard
    - shortcut-keys
post_format: []
tags:
    - 'shortcut-keys,keyboard'
---
When using the command prompt console in Linux/Unix, then one quickly gets used to the TAB-key being able to complete the name of the file or directory that reside in the current directory. For example one is standing in the root directory "C:\\", and wants to change directory to "C:\\Windows". This can be done by writing "CD W" and then press the TAB-key, which will replace "W" with the first file or directory that starts with "W".  
  
 To specify which shortcut-key that should be used for file- and directory-completion add/update these DWORD registry values:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Command Processor\]  
>  CompletionChar= 9 (ASCII value for TAB)  
>  PathCompletionChar= 9 (ASCII value for TAB)

 Another way to get completion is to start Cmd.exe like this, where you will use CTRL+D(ASCII value 4) to complete pathname and CTRL+F(ASCII value 6) to complete filename:
 > cmd /f:on

 More Info [MS KB244407](http://support.microsoft.com/kb/244407 "How to Enable Automatic Complete for the Command Prompt (Cmd.exe) [Q244407]")  
 More Info [MS KB310530](http://support.microsoft.com/kb/310530 "HOW TO: Use Automatic Completion with a Command Prompt in Windows XP [Q310530]")  