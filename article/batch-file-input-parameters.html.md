---
title: 'Using batch file input parameters'
date: '2001-01-01T11:33:39+01:00'
status: publish
permalink: /article/batch-file-input-parameters.html
author: Snakefoot
excerpt: 'How batch files gets input parameters and how to access these parameters in the batch file.'
type: post
id: 69
category:
    - Tips
tag:
    - batch-file
    - environment-variables
    - input-parameters
post_format: []
tags:
    - 'batch-file,input-parameters,environment-variables'
---
Many programs are able to handle input parameters, which one can specify when launching the program from the command line. This usually makes the program more generic and a better tool to work with (Ex. giving "a:" as parameter):

> Format a:

 When starting a [batch file](/article/batch-file.html), then one can also specify input parameters. The parameters can be accessed by the batch file like [environment variables](/article/environment-variables.html), and have the values %1 to %9.  
  
 To check if a parameter is given:
 > IF "%1"!="" ECHO Got %1

 More Info [MS KB71247](http://support.microsoft.com/kb/71247 "Semicolon, Equal Sign As Arguments in Batch File [Q71247]")  
  
 Note there also exists the input parameter %0, which is actually the batch-filename it self.  
  
 Note one can also use the SHIFT command incase the input parameter doesn't have to be in a certain order. SHIFT moves the parameter one to the left so %1 disappears, %2 becomes %1, %3 becomes %2 and etc. This behavior can be useful when having a batch file which receives an undefined order or amount of parameters. > :PARSELOOP  
>  IF "%1"=="" GOTO ENDPARSE  
>  IF "%1"=="DEBUG" SET BUILD=DEBUG  
>  IF "%1"=="RELEASE" SET BUILD=RELEASE  
>  SHIFT  
>  GOTO PARSELOOP  
>  :ENDPARSE