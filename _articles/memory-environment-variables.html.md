---
title: 'Configure the memory allocated for environment variables'
date: '2000-01-01T00:11:20+01:00'
permalink: /article/memory-environment-variables.html
author: Snakefoot
excerpt: 'How to increase the memory available for environment variables at the expense of conventional memory.'
type: post
id: 57
categories:
    - ms-dos_tips
tags:
    - conventional-memory
    - environment-variables
---
The memory available for [environment variables](/article/environment-variables.html) is limited. If requesting memory beyond the limit the following error is given:

> Out of environment space  
>   
>  Not Enough Environment Space

 The limit can be increased (In trade for Conventional memory) by editing the CONFIG.SYS and insert/update this line:
 
> REM The /E:1024 assigns 1024 bytes to SET which allows one  
>  REM to store all the 3DFX Voodoo glide settings and others  
>  SHELL=C:\\COMMAND.COM C:\\ /E:1024 /P

 More Info <a href="https://www.bing.com/search?q=KB%20105668%20Q105668" rel="nofollow" title="Windows Err Msg: Not Enough Environment Space [Q105668]">MS KB105668</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20161564%20Q161564" rel="nofollow" title="How to Adjust MS-DOS Application Environment Size [Q161564]">MS KB161564</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20230205%20Q230205" rel="nofollow" title="Out of Environment Space Error Message in MS-DOS Programs [Q230205]">MS KB230205</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20261825%20Q261825" rel="nofollow" title="'Out of Environment Space' Running Batch File or Command Prompt [Q261825]">MS KB261825</a>  