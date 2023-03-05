---
title: 'Executing program without specifying path'
date: '2000-01-01T22:46:03+01:00'
status: publish
permalink: /article/executing-program-path.html
author: Snakefoot
excerpt: 'Description of the PATH environment variable, and how to configure it.'
type: post
id: 52
category:
    - Tips
tag:
    - environment-variables
    - path
post_format: []
tags:
    - 'path,environment-variables'
---
When starting a program from the command line, then one is required to either change directory (ex. CD C:\\Game) to the location of the program, or specify the entire path when executing the program (ex. C:\\Game\\Fun.exe).  
  
 There are certain programs which can be accessed no matter what directory the command prompt is currently at (ex. format). This is possible because these programs are placed in a directory, which is included in the PATH [environment variable](/article/environment-variables.html).  
  
 When executing a command from the command line, then it first searches the internal commands (like CD, DIR, etc.), then it searches the current directory and then it searches all the directories specified by the PATH variable.  
  
 If having directory with useful utilities or [batch files](/article/batch-file.html), then it can be a good idea to extend the PATH variable so it also includes these directories:

> REM \*\*\* The %PATH% does that the original path is remembered \*\*\*  
>  SET PATH=%PATH%;C:\\BATCH;C:\\TOOLS\\NC;C:\\PACKUTIL

 Note that it is important to consider the order of the directories in the PATH variable. One should avoid adding too many directories to the PATH variable, and one should avoid adding directories which contains many files. The operating system directories should also be placed first in the PATH variable as they are probably the most used paths.  
  
 Note the PATH variable is also used in Windows and makes it possible to launch programs from the Start Menu -&gt; Run... without specifying path to the program.  
  
 More Info [MS KB97595](http://support.microsoft.com/kb/97595 "MS-DOS 6.0 and 6.2: PATH Not Limited to 128 Characters [Q97595]")  