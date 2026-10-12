---
title: 'Use environment variables for user input in Windows NT'
date: '2006-02-04T22:26:08+01:00'
permalink: /article/winnt-command-prompt-choice.html
author: Snakefoot
excerpt: 'Allow user interaction in command prompt scripts using environment variables.'
type: post
id: 462
categories:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tags:
    - batch-file
    - environment-variables
    - user-input
---
It can be useful sometimes to provide the user with a [choice](/article/choice-user-input.html) when running batch file from the command prompt (cmd.exe). This can be done with this command that prompts the user for input from the console and saves it in an [environment variable](/article/winnt-environment-variables.html):

> :choice  
> **set /p your\_choice="Please enter your choice (1,2,3): "**  
>  if %your\_choice%==3 goto option3  
>  if %your\_choice%==2 goto option2  
>  if %your\_choice%==1 goto option1  
>  echo Unrecognized option: %your\_choice%  
>  goto choice  
>   
>  :option3  
>  echo 3  
>  goto exit  
>   
>  :option2  
>  echo 2  
>  goto exit  
>   
>  :option1  
>  echo 1  
>  goto exit  
>   
>  :exit  
>  set your\_choice=