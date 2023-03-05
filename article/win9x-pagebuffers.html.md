---
title: 'Configure the asynchronous disk access buffer'
date: '2000-01-01T19:35:52+01:00'
status: publish
permalink: /article/win9x-pagebuffers.html
author: Snakefoot
excerpt: 'How to increase the size of the page buffer to hold more memory pages when doing disk access.'
type: post
id: 92
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
post_format: []
tags:
    - disk-performance
---
Windows 9x allocates by default for 4 memory pages to use for asynchronous read/write. There is a parameter to configure how many concurrent memory pages there should be allocated. The possible values are: 4, 8, 16, 32. Increasing the value will allow better disk read/write performance.  
  
 Edit the SYSTEM.INI and the following to the \[386Enh\] section:

> \[386Enh\]  
>  PageBuffers = 32

 Note this parameter should only be used if having enabled 32 bit disk access and using a permanent swap file.