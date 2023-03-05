---
title: 'Configure the amount of spare stack pages'
date: '2001-01-01T00:07:54+01:00'
status: publish
permalink: /article/win9x-stack-pages.html
author: Snakefoot
excerpt: 'Increasing the amount of spare stack pages to handle stack overflow by bad drivers.'
type: post
id: 171
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - stack-pages
post_format: []
tags:
    - stack-pages
---
There is a number of memory pages set a side to handle stack overflows to avoid crash. If all the spare pages are used then the computer will crash with the following message:

> *There are no spare stack pages. It may be necessary to increase the setting of 'MinSPs' in System.ini to prevent possible stack faults. There are currently &lt;nnn&gt; SPs allocated.  
>   
>  Windows Terminating thread due to a stack overflow problem. A VxD, possibly recently installed, has consumed too much stack space. Increase the setting of MinSPs in System.INI or remove recently installed VxDs. There are currently &lt;nnn&gt; SPs allocated.*

 This is usually caused by badly written device drivers, which have memory leaks. If one can't find out what driver is causing it and can replace it with a better one, then Add/update this line in the SYSTEM.INI in the \[386Enh\] section :  
> \[386Enh\]  
>  MinSPs=4

 Increase the MinSPs with increment of 4 until the errors stops coming. This setting has nothing to do with [STACKS=](/article/load-environment-high-memory.html) in the CONFIG.SYS (Though if STACKS= is set too low, then it can also introduce stack overflow in Windows)  
  
 More Info [MS KB145799](http://support.microsoft.com/kb/145799 "How to Troubleshoot Windows Internal Stack Overflow Error Messages [Q145799]")  
 More Info [MS KB149083](http://support.microsoft.com/kb/149083 "Error Message: There Are No Spare Stack Pages [Q149083]")  