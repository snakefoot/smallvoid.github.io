---
title: 'Check if a file or folder exists'
date: '2000-01-01T11:21:41+01:00'
status: publish
permalink: /article/check-file-dir-exists.html
author: Snakefoot
excerpt: 'How to check if a filename or directory exists'
type: post
id: 68
category:
    - Tips
tag: []
post_format: []
---
It can be useful in [batch files](/article/batch-file.html) to know whether a file or folder exists. One can use files as semaphores and for inter proces communication (IPC).  
  
 To check if a file exists:

> IF EXIST c:\\windows\\win.com ECHO File exists!

 To check if a directory exists (Notice the nul):
 
> IF EXIST c:\\windows\\nul ECHO Directory exists!

 Note if working with long directory names with spaces, then one needs to put quotes around the directory-/file-path (Notice that nul should not be included):
 > IF EXIST "C:\\Program Files\\" ECHO Directory exists!

 More Info [MS KB65994](http://support.microsoft.com/kb/65994 "Testing If a Drive or Directory Exists from a Batch File")  