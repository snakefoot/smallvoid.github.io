---
title: 'Run commands automatically at command prompt start'
date: '2003-02-28T21:45:12+01:00'
status: publish
permalink: /article/winnt-command-prompt-autorun.html
author: Snakefoot
excerpt: 'Execute commands when opening the command prompt to configure the command prompt or the environment.'
type: post
id: 461
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - autorun
post_format: []
tags:
    - autorun
---
When opening a command prompt (cmd.exe) console, then it checks the following STRING values in the registry to see if any commands should be executed:

> \[HKEY\_CURRENT\_USER \\SOFTWARE \\Microsoft \\Command Processor\]  
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Command Processor\]  
>  Autorun = "prompt \[%computername%\]$S$P$G &amp;&amp; COLOR 0A &amp;&amp; CD C:\\"

 Note the commands above will change the [command prompt](/article/winnt-command-prompt-style.html) and [color](/article/winnt-command-prompt-color.html) and change the default path/directory when opening the command prompt to the root of the C-drive.  
  
 Note to specify several commands separate them with &amp;&amp;, or use a batch file like a Autoexec.bat.  
  
 Note the cmd has a switch to disable the execution of the Autorun:
 > cmd /d

 Credits [jsifaq.com](http://jsifaq.com/)