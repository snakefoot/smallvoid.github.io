---
title: 'Easy compressing and extracting using batch files'
date: '2000-01-01T23:30:43+01:00'
status: publish
permalink: /article/pkunzip-pkzip-batch.html
author: Snakefoot
excerpt: 'How to wrap a batch file around the pkzip and pkunzip command line utiltities.'
type: post
id: 55
category:
    - Tips
tag:
    - backup
    - batch-file
    - compress
    - extract
    - pkunzip
    - pkzip
    - restore
post_format: []
tags:
    - 'pkzip,pkunzip,batch-file,backup,restore,compress,extract'
---
[PKZIP and PKUNZIP](http://www.pkware.com/) command line utilities for handling zip files, are not the most intuitive. Instead of having to remember the proper command line parameters, for either compressing files into a zip file, or to extract the files again from a zip file, then one can put them in a [batch file](/article/batch-file.html).  
  
 Create a batch file called ZIP.BAT containing the following lines:
> @ECHO OFF  
>  REM \*\*\* If no parameters then compress all files into ZIPFILE.ZIP  
>  IF "%1"=="" GOTO NONAME  
>  REM \*\*\* If one parameter(filename) then compress all files into filename  
>  IF "%2"=="" GOTO ALL  
>   
>  REM \*\*\* Both filename to compress to is given and files to compress \*\*\*  
>  PKZIP -a -ex -r -P -whs %1 %2 %3 %4 %5 %6 %7 %8 %9  
>  GOTO EXIT  
>   
>  :ALL  
>  PKZIP -a -ex -r -P -whs %1 \*.\*  
>  GOTO EXIT  
>   
>  :NONAME  
>  PKZIP -a -ex -r -P -whs ZIPFILE.ZIP \*.\*  
>   
>  :EXIT

 Create a batch file called UZIP.BAT containing the following lines:
> @ECHO OFF  
>  REM \*\*\* If no parameters then extract all the zip files \*\*\*  
>  IF "%1"=="" GOTO ALL  
>  REM \*\*\* If only one parameter given then extract to current directory \*\*\*  
>  IF "%2"=="" GOTO HERE  
>   
>  REM \*\*\* Two or more parameters given, the 1st is the zip file, the 2nd is the destination \*\*\*  
>  PKUNZIP.EXE -d %1 -o %2  
>  GOTO EXIT  
>   
>  :HERE  
>  PKUNZIP.EXE -d %1 -o .\\  
>  GOTO EXIT  
>   
>  :ALL  
>  PKUNZIP.EXE -d \*.ZIP -o .\\UZIP\\  
>   
>  :EXIT