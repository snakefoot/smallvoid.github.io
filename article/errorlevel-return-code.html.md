---
title: 'Using Errorlevel to handle program return code'
date: '2002-03-01T10:08:35+01:00'
status: publish
permalink: /article/errorlevel-return-code.html
author: Snakefoot
excerpt: 'How to check the ERRORLEVEL variable to get the return code of a program.'
type: post
id: 64
category:
    - Tips
tag:
    - batch-file
    - errorlevel
    - return-code
post_format: []
tags:
    - 'errorlevel,return-code,batch-file'
---
When running a command line program from a [batch file](/article/batch-file.html), then the program will end with a return code, which usually specifies whether the program succeeded. One can catch the return code and use it in the batch file.

> @ECHO OFF  
>  DB2 CONNECT TO MY\_DB  
>  IF ERRORLEVEL 1 GOTO ERROR  
>  IF ERRORLEVEL 0 GOTO SUCCESS  
>   
>  :SUCCESS  
>  ECHO SUCCESS  
>  GOTO EXIT  
>   
>  :ERROR  
>  ECHO ERROR  
>  GOTO EXIT  
>   
>  :EXIT

 Note one should always check the highest errorlevel first. Because the errorlevel check is less or equal. So if a program returns 15 and one checks if errorlevel==0 then it would return true.  
  
 Note one should use GOTO when doing errorlevel checking. Because if not, then it will continue to check the errorlevels below the one it matches.  
  
 Related [Access selection from CHOICE using ERRORLEVEL](/article/choice-user-input.html)  
  
 More Info [MS KB69576](http://support.microsoft.com/kb/69576 "Testing for a Specific Error Level in Batch Files [Q69576]")  
  
 Note one can also pipe the different types of errorlevel codes to a file:
 
> DB2 CONNECT TO MY\_DB 1&gt;&gt;error.txt 2&gt;&gt;error.txt