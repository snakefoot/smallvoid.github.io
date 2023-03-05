---
title: 'Configure the memory allocated for environment variables'
date: '2000-01-01T00:11:20+01:00'
status: publish
permalink: /article/memory-environment-variables.html
author: Snakefoot
excerpt: 'How to increase the memory available for environment variables at the expense of conventional memory.'
type: post
id: 57
category:
    - Tips
tag:
    - conventional-memory
    - environment-variables
post_format: []
tags:
    - 'environment-variables,conventional-memory'
---
The memory available for [environment variables](/article/environment-variables.html) is limited. If requesting memory beyond the limit the following error is given:

> Out of environment space  
>   
>  Not Enough Environment Space

 The limit can be increased (In trade for Conventional memory) by editing the CONFIG.SYS and insert/update this line:
 
> REM The /E:1024 assigns 1024 bytes to SET which allows one  
>  REM to store all the 3DFX Voodoo glide settings and others  
>  SHELL=C:\\COMMAND.COM C:\\ /E:1024 /P

 More Info [MS KB105668](http://support.microsoft.com/kb/105668 "Windows Err Msg: Not Enough Environment Space [Q105668]")  
 More Info [MS KB161564](http://support.microsoft.com/kb/161564 "How to Adjust MS-DOS Application Environment Size [Q161564]")  
 More Info [MS KB230205](http://support.microsoft.com/kb/230205 "Out of Environment Space Error Message in MS-DOS Programs [Q230205]")  
 More Info [MS KB261825](http://support.microsoft.com/kb/261825 ""Out of Environment Space" Running Batch File or Command Prompt [Q261825]")  