---
title: 'MEM with enhanced listing of conventional memory'
date: '2000-01-01T23:02:15+01:00'
status: publish
permalink: /article/mem-conventional-memory.html
author: Snakefoot
excerpt: 'Description of the special switch for MEM to diagnose conventional memory usage, and how to put it in a batch file.'
type: post
id: 53
category:
    - Tips
tag:
    - batch-file
    - conventional-memory
    - device-driver
    - terminate-stay-resident
post_format: []
tags:
    - 'conventional-memory,terminate-stay-resident,device-driver,batch-file'
---
Many times when wanting to run a DOS game/program, then one gets the error message: "Not enough conventional memory to run". To solve this error one first have to find out what is currently occupying the memory, and then consider what [drivers to load in high memory](/article/load-drivers-high-memory.html) or remove from memory.  
  
 By default when running the command MEM, then one only sees the currently available conventional memory. But there exists a switch, that can be used to display the exact device drivers loaded and how much memory they use.  
  
 Instead of having to remember this special switch, then one can make a [batch file](/article/batch-file.html) called MEO.BAT with the following lines:

> @REM \*\*\* Show TSRs memory usage \*\*\*  
>  @MEM.EXE /C |more