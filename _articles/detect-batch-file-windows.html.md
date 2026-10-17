---
title: 'Detect if a batch file is executed within Windows'
date: '2000-01-01T18:47:03+01:00'
permalink: /article/detect-batch-file-windows.html
author: Snakefoot
excerpt: 'How to use environment variables to detect that a batch file is executed within Windows.'
type: post
id: 47
categories:
    - ms-dos_tips
tags:
    - batch-file
---
It is possible to detect within a batch file if it was executed in a Windows environment. This is done by checking for the environment variable **WINDIR**, which is exists in the Windows environment. This can be used ex. if having an application that cannot execute properly in the Windows environment:

> @EHCO OFF  
>  IF NOT "%WINDIR%"=="" GOTO EXIT  
>  DOSPROG.EXE  
>  :EXIT

 More Info <a href="https://www.bing.com/search?q=KB+85469+Q85469" rel="nofollow" title="How to Detect Windows Mode and Version from a Batch File [Q85469]">MS KB85469</a>  
  
 Note one can also check whether one is executing in Windows NT or Windows 9x. This is done by checking for the enviroment variable **SYSTEMROOT**, which is created by the Windows NT enviroment:
 
>  @EHCO OFF  
>  IF NOT "%SYSTEMROOT%"=="" GOTO WINNT  
>  IF NOT "%WINDIR%"=="" GOTO WIN9X  
>  GOTO DOS

 More Info <a href="https://www.bing.com/search?q=KB+190899+Q190899" rel="nofollow" title="How to Determine the OS Type in a Logon Script [Q190899]">MS KB190899</a>