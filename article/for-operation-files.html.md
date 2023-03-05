---
title: 'Using FOR to perform an operation on a file collection'
date: '2002-03-01T11:48:14+01:00'
status: publish
permalink: /article/for-operation-files.html
author: Snakefoot
excerpt: 'How to use the FOR keyword to perform an operation on a collection of files that matches a wildcard.'
type: post
id: 70
category:
    - Tips
tag:
    - batch-file
post_format: []
tags:
    - batch-file
---
The FOR command allows one to specify a file wildcard (\*.txt) and what operation to perform on each file that matches the wildcard (type).  
  
 When using the FOR loop directly from the command prompt:

> FOR %f IN (\*.txt) DO type %f

 When using FOR inside af [batch file](/article/batch-file.html):
 
 > FOR %%f IN (\*.txt) DO type %%f

 Related [Create your own file find utility using FOR](/article/file-search-utility.html)  
  
 More Info [MS KB68268](http://support.microsoft.com/kb/68268 "Simulating Wildcards [Q68268]")  
 More Info [MS KB75634](http://support.microsoft.com/kb/75634 "Percent Signs Stripped from Batch File Text [Q75634]")  
 More Info [MS KB134572](http://support.microsoft.com/kb/134572 "FOR Command Behaves Differently From Previous MS-DOS Versions [Q134572]")  