---
title: 'Environment variables'
date: '2003-02-22T19:08:44+01:00'
status: publish
permalink: /article/environment-variables.html
author: Snakefoot
excerpt: 'Description of environment variables and how to configure them.'
type: post
id: 48
category:
    - Tips
tag:
    - batch-file
    - environment-variables
post_format: []
tags:
    - 'environment-variables,batch-file'
---
In the DOS environment memory is reserved for user defined variables. Enviroment variables can be used for different things:

- [Batch files](/article/batch-file.html) can use them for temporary storing values during executions. 
  - When creating environment variables in a batch file, then one must remember to clear them again before exiting, or else they continue to live on and consume memory after the batch file have executed.
- Global variables specified in Autoexec.bat, which affects the behavior of the DOS environment and programs executed within the environment: 
  - [Changing the temporary directory](/article/temporary-directory.html).
  - [Changing the list style of the dir command](/article/list-style-dir-command.html).
  - [Execute programs without specifying path](/article/executing-program-path.html).
 
 To list all environment variables in memory:
 
> SET | more

 To show the value of a single environment variable:
 
> SET CLASSPATH  
>   
> ECHO %CLASSPATH%

 To change the value or create a single environment variable:
 
> SET CLASSPATH=.;C:\\JDK

 To append to an existing environment variable:
 
> SET CLASSPATH=%CLASSPATH%;C:\\MY\_JAVA

 To clear or delete a single environment variable:
 
 > SET CLASSPATH=

 Note when using SET from the command prompt then the environment variable will only live temporarily and will be forgotten when the command environment closes. To make a permanent environment variable move the SET of the variable to the AUTOEXEC.BAT.  
  
 Related [Configure how much memory to allocate for environment variables](/article/memory-environment-variables.html)  
 Related [Batch file input parameters are accessed like environment variables](/article/batch-file-input-parameters.html)  
  
 More Info [MS KB36605](http://support.microsoft.com/kb/36605 "Environment Variable Trailing Spaces Not Truncated [Q36605]")  
 More Info [MS KB41246](http://support.microsoft.com/kb/41246 "How to Use Environment Variable Substitution in Batch Files [Q41246]")  
 More Info [MS KB66292](http://support.microsoft.com/kb/66292 "Reading Text Files into MS-DOS Environment Variables [Q66292]")  
 More Info [MS KB121170](http://support.microsoft.com/kb/121170 "How to Access Environment Variables in an MS-DOS Batch File [Q121170]")  
 More Info [MS KB153163](http://support.microsoft.com/kb/153163 "Using MS-DOS Environment Variable as Command-Line Option [Q153163]")  