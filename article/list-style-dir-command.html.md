---
title: 'Changing the list style of the dir command'
date: '2000-01-01T22:34:16+01:00'
status: publish
permalink: /article/list-style-dir-command.html
author: Snakefoot
excerpt: 'How to change the listing of files and folders when using the dir command with an environment variable.'
type: post
id: 51
category:
    - Tips
tag: []
post_format: []
tags:
    - ''
---
DIR is an internal command recognized by the command prompt interpreter, and it displays the contents of directory (sub-folders and files). It is possible to format the output of the DIR command by setting an [environment variable](/article/environment-variables.html).  
  
 Edit AUTOEXEC.BAT and insert/update these line:

> REM /A show all files(System/hidden), /O sort with B(directories first)  
>  REM and N(By name), /P pause for each screen  
>  SET DIRCMD=/A/OGN/P

 To get a full list of all the settings available for the DIR command:
 
 > DIR /?