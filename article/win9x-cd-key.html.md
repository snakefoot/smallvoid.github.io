---
title: 'Retrieve a lost CD-Key from the registry'
date: '2003-02-28T00:50:20+01:00'
status: publish
permalink: /article/win9x-cd-key.html
author: Snakefoot
excerpt: 'Where to find the cd-key for the current Windows install.'
type: post
id: 162
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - cd-key
post_format: []
tags:
    - cd-key
---
The CD-key entered during installation is stored in the registry (and cannot be found on the install CD). One can extract the CD-key from an existing installation as it is saved as pure text in the registry, but some might find it easier to use [KeyFinder](/article/cd-key-registry.html).  
  
 In Windows 95 it is called Product Id:
> \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Windows \\CurrentVersion\]  
>  ProductID=

 In Windows 98/Me it is called Product Key:
> \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Windows \\CurrentVersion\]  
>  ProductKey=

 Note one can also use [REGEDIT.EXE](/article/win95-regedit.html) in DOS to extract the contents of the registry file C:\\Windows\\System.dat to a text registry file, and then use EDIT.EXE to search the text file for the above registry key.