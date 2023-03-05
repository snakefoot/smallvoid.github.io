---
title: 'Reserve the upper memory block to free conventional memory'
date: '2000-01-01T19:12:17+01:00'
status: publish
permalink: /article/win9x-umb-dos.html
author: Snakefoot
excerpt: 'How to reserve the upper memory block and load the dos enviroment in high memory to free conventional memory.'
type: post
id: 90
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - conventional-memory
    - upper-memory-block
post_format: []
tags:
    - 'upper-memory-block,conventional-memory'
---
By default Windows uses all the memory it can get its hands on including the [UMB](/article/upper-memory-block-umb.html). It is possible to force Windows not to use the UMB, so the DOS enviroment can be loaded in high memory and save conventional memory.  
  
 Select "Run..." in the Start Menu and run SYSEDIT.EXE. Select the file SYSTEM.INI, find the section \[386enh\] and write the following:

> \[386enh\]  
>  LocalLoadHigh = 1

 Note this will only provide a benefit when running DOS games/programs within Windows.