---
title: 'Configure conservative swap file usage'
date: '2000-01-01T20:04:37+01:00'
status: publish
permalink: /article/win9x-conservative.html
author: Snakefoot
excerpt: 'How to configure the page algorithm, so it will not perform paging when the system is idle.'
type: post
id: 94
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - page-algorithm
    - page-file
    - swap-file
post_format: []
tags:
    - 'page-algorithm,swap-file,page-file'
---
Windows 98 introduced a new feature called PageFile\_Call\_Async\_Manager. It will detect when there is little system activity, and then start to unload pages from the physical memory (RAM) and write them to the swap file on the hard disk. This can be useful if having limited memory, as this feature will increase the chance that there is RAM enough for the applications running.  
  
 But even if having enough RAM, then it still tries to keep as much of the RAM free. Accessing memory which have been unloaded to the swap file is extremely slow, therefore one will experience slow downs every time Windows 98 have unloaded page to the swap file, which an application suddenly need.  
  
 Therefore if having enough RAM to satisfy the normal operation (64 MByte+), then it can be a good idea to disable the automatic unloading of memory pages to disk and instead activate the old conversative swap file usage. This is done by editing the System.ini file and adding the following line to the \[386enh\] section:

> \[386Enh\]  
>  ConservativeSwapfileUsage = 1

 More Info [MS KB223294](http://support.microsoft.com/kb/223294 "INFO: The Windows 98 PageFile_Call_Async_Manager Service [Q223294]")  
  
 Related [Improve your permanent page file](/article/win9x-pagebuffers.html)  
 Related [Configure the page file for best performance](/article/windows-page-file.html)  