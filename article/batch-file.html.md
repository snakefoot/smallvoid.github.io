---
title: 'Writing a batch file'
date: '2000-01-01T16:45:33+01:00'
status: publish
permalink: /article/batch-file.html
author: Snakefoot
excerpt: 'How to write a batch file with description of different commands available.'
type: post
id: 46
category:
    - Tips
tag:
    - batch-file
post_format: []
autometa:
    - ''
tags:
    - batch-file
---
A batch file is a small script that can be used to perform several commands, or simplify a complex command which requires many parameters. One executes the batch file like one executes a normal exe-file.  
 To write a batch file, one has to use a simple text-editor and when saving the script then give it the proper file extension ".BAT". When writing the batch file one can make use of different builtin commands:

<table border="1"><tr><th>Keyword</th><th>Functionality</th></tr><tr><td>[ECHO](/article/echo-output.html)</td><td>Displays a text string</td></tr><tr><td>REM</td><td>Used to comment out a command or make a remark</td></tr><tr><td>[SET](/article/environment-variables.html)</td><td>Saves a value in an environment variables</td></tr><tr><td>GOTO</td><td>Jumps to a :LABEL, which can be used to make loops or function calling</td></tr><tr><td>IF</td><td>Allows conditional behavior</td></tr><tr><td>CALL</td><td>Used for calling other batch files</td></tr><tr><td>[FOR](/article/for-operation-files.html)</td><td>Performs a command on a collection of items</td></tr><tr><td>[ERRORLEVEL](/article/errorlevel-return-code.html)</td><td>Contains the returncode of an excuted program</td></tr><tr><td>[%1-%9](/article/batch-file-input-parameters.html)</td><td>When calling a batch one can provide parameters, which the batch file can access as environment variables</td></tr><tr><td>PAUSE</td><td>Stops the execution of the batch file until the user presses a key on the keyboard</td></tr></table>

 Examples of possible ways to use batch files:
- [Enhanced dir command](/article/dir-list-executables.html)
- [Enhanced mem command](/article/mem-conventional-memory.html)
- [Easy compressing and extracting using batch files](/article/pkunzip-pkzip-batch.html)
- [Find file utility](/article/file-search-utility.html)
 
 Tricks one can use to enhance a batch file:
- [Detect if a batch file is executed within Windows](/article/detect-batch-file-windows.html)
- [Get user input with CHOICE](/article/choice-user-input.html)
- [Create your own sleep / wait program](/article/sleep-command.html)
- [Create or modify text files with TYPE](/article/type-text-file.html)
- [Detecting whether a file or folder exists](/article/check-file-dir-exists.html)