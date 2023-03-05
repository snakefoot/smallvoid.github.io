---
title: 'Remove warning about modifying contents in the Windows-folder'
date: '2001-01-01T23:38:26+01:00'
status: publish
permalink: /article/windows-folder-warning.html
author: Snakefoot
excerpt: 'Active Desktop makes it posssible to customize folders, and so the Windows folder is customized to avoid messing with the Windows system files.'
type: post
id: 303
category:
    - Desktop
    - Desktop
    - Desktop
tag:
    - active-desktop
post_format: []
tags:
    - active-desktop
---
With the introduction of the Active desktop it became possible to configure how folders should be displayed when using explorer.  
  
 Microsoft uses this feature to keep the clueless users to the beaten path, when they go exploring their harddrive using explorer. When trying to enter a Windows system folder one gets the following message:

> *Warning - Modifying the contents of this folder may cause your programs to stop working correctly.To view the contents of this folder, click Show Files*

 One can disable this warning by renaming the following file which resides inside the folder giving the warning:
 > folder.htt

 More Info [MS KB181689](http://support.microsoft.com/kb/181689 "INFO: Purpose and Format of Folder.htt [Q181689]")  
 More Info [MS KB182000](http://support.microsoft.com/kb/182000 "How to Customize a Folder for Web View [Q182000]")  
 More Info [MS KB184785](http://support.microsoft.com/kb/184785 "Windows 98 Program Files Folder Is Displayed Incorrectly [Q184785]")  
 More Info [MS KB228035](http://support.microsoft.com/kb/228035 "Removing the "Show Files" Link in Windows Explorer [Q228035]")  
  
 Credits [win98central.com](http://win98central.com/)