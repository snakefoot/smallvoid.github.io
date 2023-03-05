---
title: 'Enhanced DIR that only lists executables'
date: '2000-01-01T23:25:38+01:00'
status: publish
permalink: /article/dir-list-executables.html
author: Snakefoot
excerpt: 'How to create a batch file that works like a dir command but only lists executables.'
type: post
id: 54
category:
    - Tips
tag:
    - batch-file
post_format: []
tags:
    - batch-file
---
When having several DOS programs/games installed, then it is not always easy to remember the executable file needed to start a certain program/game. To help in this situation, one can create a batch file that list the available executable files in the current directory (Ex. BAT, COM, EXE).  
  
 Make a [batch file](/article/batch-file.html) called DEX.BAT containing the following lines:

> @ECHO OFF  
>  REM \*\*\* %1 makes it possible to specify the /S option (With sub-directories) \*\*\*  
>  IF EXIST \*.BAT DIR \*.BAT /B %1  
>  IF EXIST \*.COM DIR \*.COM /B %1  
>  IF EXIST \*.EXE DIR \*.EXE /B %1