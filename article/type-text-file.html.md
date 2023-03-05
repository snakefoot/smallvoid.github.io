---
title: 'Using TYPE to create and edit text files'
date: '2000-01-01T11:10:01+01:00'
status: publish
permalink: /article/type-text-file.html
author: Snakefoot
excerpt: 'How to use the TYPE command to perform file manipulation on text files.'
type: post
id: 67
category:
    - Tips
tag: []
post_format: []
tags:
    - ''
---
TYPE is a command that can output the contents of a text file. The output of TYPE can then be used to modify other files, which can be used in [batch files](/article/batch-file.html).  
  
 To display the contents of a text file (Old.bat) with TYPE:
 > TYPE Old.bat | MORE

 To create a copy of a file (Old.bat) to or overwrite an existing (New.bat):
 > TYPE Old.bat &gt; New.bat

 To append the contents of one file (Old.bat) to another file (New.bat):
 > TYPE Old.bat &gt;&gt; New.bat

 To create an empty file:
 > TYPE nul &gt; New.bat

 Remember though that it will only work with text-files, not with binary files.  
  
 Related [Using ECHO to modify text files](/article/echo-output.html).