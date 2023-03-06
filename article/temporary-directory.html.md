---
title: 'Changing the temporary directory'
date: '2000-01-01T22:22:04+01:00'
status: publish
permalink: /article/temporary-directory.html
author: Snakefoot
excerpt: 'Description of the temporary directory, and how to change the location using environment variables.'
type: post
id: 50
category:
    - Tips
tag:
    - environment-variables
    - free-disk-space
    - temporary-directory
post_format: []
tags:
    - 'temporary-directory,environment-variables,free-disk-space'
---
The temporary directory is specified by two [environment variables](/article/environment-variables.html) called **TMP** and **TEMP**. When an application or [batch file](/article/batch-file.html) have to create an temporary file, then they can use one of these variables to get the path of the temporary directory.  
  
 To move the TEMP directory to another folder/partition/HDD edit the file AUTOEXEC.BAT and insert/update these lines (Best to place them in the top of the file):

> REM \*\*\* Places all temporary files in the directory D:\\TEMP \*\*\*  
>  SET TEMP=D:\\TEMP  
>  SET TMP=D:\\TEMP

 Note the temporary directory is a location where files often are created and deleted. Some times it can be useful to move the temporary directory to another location.
- The partition holding the temporary directory is low on free space.
- File fragmentation introduced by the temporary directory is better placed on another partition.
- There exist another partition which is much faster.
 
 Note that many programs likes to create files in the TEMP directory, but few remembers to delete them again. Therefore it can be a good idea to clean the TEMP directory at bootup. This can be done by adding these lines to the AUTOEXEC.BAT (Below the lines that specifies TMP and TEMP):
> ECHO Clearing TEMP directory : %TEMP%  
>  DELTREE /Y %TEMP%\\\*.\* &gt;NUL

 More Info [MS KB130075](http://support.microsoft.com/kb/130075 "TEMP Environment Variable Overwritten in Command Prompt [Q130075]")  