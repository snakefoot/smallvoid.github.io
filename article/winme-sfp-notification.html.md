---
title: 'System file protection notifications in Windows Me'
date: '2001-02-01T00:38:58+01:00'
status: publish
permalink: /article/winme-sfp-notification.html
author: Snakefoot
excerpt: 'Display popup when System File Protection in Windows Me is activated.'
type: post
id: 174
category:
    - Troubleshoot
tag:
    - system-file-protection
post_format: []
tags:
    - system-file-protection
---
You can be notified of the following changes :

- Restoring a protected file
- Removing a security catalog
- Adding a security catalog
 
 Edit the registry :  
> \[HKey\_Local\_Machine\\ Software\\ Microsoft\\ Windows\\ CurrentVersion\\ SystemFileProtection\]  
>  ShowPopups = 1 (Default = 0)

 More Info [MS KB266077](http://support.microsoft.com/kb/266077 "How to Enable System File Protection Popup Notification [Q266077]")  
  
 Credits [onecomputerguy.com](http://www.onecomputerguy.com/)