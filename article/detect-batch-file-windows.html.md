---
title: 'Detect if a batch file is executed within Windows'
date: '2000-01-01T18:47:03+01:00'
status: publish
permalink: /article/detect-batch-file-windows.html
author: Snakefoot
excerpt: 'How to use environment variables to detect that a batch file is executed within Windows.'
type: post
id: 47
category:
    - Tips
tag:
    - batch-file
post_format: []
tags:
    - batch-file
---
It is possible to detect within a batch file if it was executed in a Windows environment. This is done by checking for the environment variable **WINDIR**, which is exists in the Windows environment. This can be used ex. if having an application that cannot execute properly in the Windows environment:

> @EHCO OFF  
>  IF NOT "%WINDIR%"=="" GOTO EXIT  
>  DOSPROG.EXE  
>  :EXIT

 More Info [MS KB85469](http://support.microsoft.com/kb/85469 "How to Detect Windows Mode and Version from a Batch File [Q85469]")  
  
 Note one can also check whether one is executing in Windows NT or Windows 9x. This is done by checking for the enviroment variable **SYSTEMROOT**, which is created by the Windows NT enviroment:
 
>  @EHCO OFF  
>  IF NOT "%SYSTEMROOT%"=="" GOTO WINNT  
>  IF NOT "%WINDIR%"=="" GOTO WIN9X  
>  GOTO DOS

 More Info [MS KB190899](http://support.microsoft.com/kb/190899 "How to Determine the OS Type in a Logon Script [Q190899]")