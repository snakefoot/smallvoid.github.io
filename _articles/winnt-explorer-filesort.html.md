---
title: 'Configure the explorer file sort to be like in Windows 2000'
date: '2003-01-10T20:51:55+01:00'
permalink: /article/winnt-explorer-filesort.html
author: Snakefoot
excerpt: 'Windows Explorer file sorting can be changed from logical number compare to just one digit at a time.'
type: post
id: 408
categories:
    - windows-xp_tips
    - windows-2003_tips
    - windows-vista_tips
tags:
    - desktop
    - file-sort
    - windows-explorer
---
When sorting filenames containing numbers and underscore in Windows Explorer then it inspects the entire number:

> 5.txt  
>  11.txt  
>  88.txt

 Where Win2k (and older versions) only looks at one digit at a time:
>  11.txt  
>  5.txt  
>  88.txt

 To change the filesort back to the Win2k behavior, set this DWORD in the registry:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\Currentversion \\Policies \\Explorer\]  
>  NoStrCmpLogical = 1 (Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20318872%20Q318872" rel="nofollow" title="Incorrect Sort Order in Windows Explorer in Windows XP [Q318872]">MS KB318872</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20319827%20Q319827" rel="nofollow" title="The Sort Order for Files and Folders Whose Names Contain Numerals Is Different in Windows XP Than It Is in Windows 2000 [Q319827]">MS KB319827</a> (Windows XP requires SP1 to recognize this setting)

 Credits [Tom Wu](mailto:Tom%20Wu<i-tomw@online.microsoft.com>)