---
title: 'Change look of the command prompt in Windows NT'
date: '2003-02-28T21:40:02+01:00'
permalink: /article/winnt-command-prompt-style.html
author: Snakefoot
excerpt: 'Description of how to extend the default command prompt to include more information than just the current directory.'
type: post
id: 460
categories:
    - windows-nt4_command-prompt
    - windows-xp_command-prompt
    - windows-2000_command-prompt
    - windows-2003_command-prompt
tags:
    - visual-style
---
Like one could change the [DOS Prompt](/article/style-dos-prompt.html) one is also able to change the command prompt (cmd.exe) console. Instead of doing it in the AUTOEXEC.BAT then it is done with an environment variable :

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager\\ Environment\]  
>  PROMPT = "$P$G"

 Note one can use [environment variables](/article/winnt-environment-variables.html) like %USERNAME% or %COMPUTERNAME% in the prompt.  
> PROMPT \[%computername%\] $P$G

 Note one can change the prompt after starting the cmd. To reset just write PROMPT with no parameters. To see all parameters write PROMPT /?.  
  
 Related [Change the color of the command prompt](/article/winnt-command-prompt-color.html)  
 Related [Change the font of the command prompt](/article/winnt-cmd-add-font.html)  
  
 Credits [regedit.com](http://regedit.com)