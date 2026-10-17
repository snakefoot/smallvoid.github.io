---
title: 'Using Choice to get user interaction'
date: '2002-03-01T10:17:47+01:00'
permalink: /article/choice-user-input.html
author: Snakefoot
excerpt: 'How to use the Choice program to present a set of options the user can choose from.'
type: post
id: 65
categories:
    - ms-dos_tips
tags:
    - batch-file
    - choice
    - errorlevel
    - return-code
    - user-input
---
MS DOS 6.0 introduced the program CHOICE, which can display a set of options and wait for the user to make a choice. When the user makes a selection the return code of CHOICE contains the selection, which can be accessed using [ERRORLEVEL](/article/errorlevel-return-code.html). This makes it possible to prompt the user for input from the command line in a [batch file](/article/batch-file.html) and react to it.

> choice /c:abc Choose an option   
>  IF ERRORLEVEL 3 GOTO OPTIONC  
>  IF ERRORLEVEL 2 GOTO OPTIONB  
>  IF ERRORLEVEL 1 GOTO OPTIONA  
>   
>  :OPTIONC  
>  ECHO C  
>  GOTO EXIT  
>   
>  :OPTIONB  
>  ECHO B  
>  GOTO EXIT  
>   
>  :OPTIONA  
>  ECHO A  
>  GOTO EXIT  
>   
>  :EXIT

 More Info <a href="https://www.bing.com/search?q=KB%2077457%20Q77457" rel="nofollow" title="Accepting Keyboard Input in Batch Files [Q77457]">MS KB77457</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2096697%20Q96697" rel="nofollow" title="Using ANSI Characters with the CHOICE Command [Q96697]">MS KB96697</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2097504%20Q97504" rel="nofollow" title="MS-DOS: No Interactive Boot Option for the AUTOEXEC.BAT File [Q97504]">MS KB97504</a>  