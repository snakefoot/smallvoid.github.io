---
title: 'Configure how many files a DOS program can have open'
date: '2001-01-01T23:09:39+01:00'
permalink: /article/winme-dos-files.html
author: Snakefoot
excerpt: 'How to increase the limit of how many files a DOS program can have open.'
type: post
id: 98
categories:
    - windows-me_performance
tags:
    - file-handles
---
By default this limit was controlled by the FILES= setting in Config.sys. Windows Me doesn't react to this setting any longer, and if using a DOS program that requires a lot of open files (More than 30), then one have to increase the limit another place.  
  
 Add this line in the file SYSTEM.INI in the section \[386Enh\]:

> \[386Enh\]  
>  PerVMFiles = 100 (Default - 30 Range 30-225)

 More Info <a href="https://www.bing.com/search?q=KB%20269030%20Q269030" rel="nofollow" title="How to Increase Available File Handles for MS-DOS-Based Programs in Windows Millennium Edition [Q269030]">MS KB269030</a>