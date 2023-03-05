---
title: 'Using ECHO for outputting'
date: '2000-01-01T01:00:33+01:00'
status: publish
permalink: /article/echo-output.html
author: Snakefoot
excerpt: 'Description of the ECHO command and the possible ways to make output.'
type: post
id: 60
category:
    - Tips
tag:
    - batch-file
post_format: []
tags:
    - batch-file
---
The ECHO command can be used to output status messages during the execution of a [batch file](/article/batch-file.html):

> ECHO Hello world...

 When executing commands in a batch file, then the command-line for the command is shown unless one specifies the following command at the top of the batch file (Note the "@" keeps the comand from being shown):
 
>  @echo off  
>  ECHO Hello world...

 To create a newline or carriage return (Notice the "."):
 
> ECHO.

 To create a beep sound in the PC-Speaker using CTRL+G (Or ASCII 7 produced by holding down ALT-key and 7-key):
 
> ECHO ^G

 To send a keystroke to a program:
 
> ECHO Y | DEL \*.\*

 To create a new file(status.txt) containing a text line:
 
> ECHO No errors detected &gt; status.txt

 To append a text line to an existing file(status.txt):
 
> ECHO Batch Program Ends &gt;&gt; status.txt

 To create a batch file inside a batch-file:
 
> ECHO ECHO Hello &gt; Hello.bat  
>  CALL Hello.bat

 To send a command to a modem connected to the COMx port:
 
>  REM \*\*\* AT = Attention, M1 = Turn speaker on, L3 = High speaker volume  
>  REM \*\*\* X0 = Do not wait for dialtone, DT12345 = Dial 12345  
>  ECHO ATM1L3X0DT12345 &gt; COMx  
>   
>  REM \*\*\* AT = Attention, H0 = Hook off the modem  
>  ECHO ATH0 &gt; COMx  
>   
>  More Info [MS KB84279](http://support.microsoft.com/kb/84279 "Testing Communications from MS-DOS [Q84279]")  
>  More Info [MS KB105940](http://support.microsoft.com/kb/105940 "Troubleshooting Serial Port Problems in Windows [Q105940]")