---
title: 'System file protection notifications in Windows Me'
date: '2001-02-01T00:38:58+01:00'
permalink: /article/winme-sfp-notification.html
author: Snakefoot
excerpt: 'Display popup when System File Protection in Windows Me is activated.'
type: post
id: 174
categories:
    - windows-me_troubleshoot
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

 More Info <a href="https://www.bing.com/search?q=KB+266077+Q266077" rel="nofollow" title="How to Enable System File Protection Popup Notification [Q266077]">MS KB266077</a>  
  
 Credits [onecomputerguy.com](http://www.onecomputerguy.com/)