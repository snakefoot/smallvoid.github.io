---
title: 'Configure the DOS prompt inside Windows 9x'
date: '2000-01-01T01:22:04+01:00'
status: publish
permalink: /article/win9x-dos-prompt.html
author: Snakefoot
excerpt: 'Using a batch file to configure the DOS prompt when starting it from the Windows desktop.'
type: post
id: 134
category:
    - Tips
    - Tips
    - Tips
tag:
    - 'MS DOS'
post_format: []
tags:
    - ms-dos
---
When opening a DOS prompt from the Windows desktop, then it will inherit the environment specified by the Autoexec.bat and Config.sys. It is possible to specify an additional [batch file](/article/batch-file.html) (besides Autoexec.bat), which should be executed when opening a DOS prompt from the Window desktop.

1. Create a batch file **WinDos.bat** with the following contents:
  > @ECHO OFF  
  >  C:\\WINDOWS\\COMMAND\\doskey
2. Create a shortcut to the **Command.com**
3. Right-click the the shortcut and select **Properties**
4. In the menu select **Program** and point it to the created **WinDos.bat**
 
 Note to make the Windows 9x startup faster, then one should consider moving the contents from the Autoexec.bat to WinDos.bat (Or at least as much as possible).  
  
 Related [Using DosStart.bat to configure DOS when leaving Windows](/article/win9x-dosstart.html)