---
title: 'Register Windows 98 without using registration wizard'
date: '2000-01-01T23:33:57+01:00'
status: publish
permalink: /article/win98-register.html
author: Snakefoot
excerpt: 'Enable the Update Wizard without performing registration.'
type: post
id: 157
category:
    - Troubleshoot
tag:
    - registration-wizard
    - update-wizard
post_format: []
tags:
    - 'registration-wizard,update-wizard'
---
If one skipped the Registration Wizard during the install of Windows 98, then the Update Wizard becomes disabled. The Update Wizard makes it easy to scan for new updates for Windows components and drivers.  
  
 Windows 98 will think it is registered when setting the following registry keys:

> \[HKEY\_LOCAL\_MACHINE\\ SOFTWARE\\ Microsoft\\ Windows\\ CurrentVersion\]  
>  RegDone = "1"  
>   
>  \[HKEY\_LOCAL\_MACHINE\\ SOFTWARE\\ Microsoft\\ Windows\\ CurrentVersion\\ Welcome\]  
>  @ = 1