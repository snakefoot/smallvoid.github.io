---
title: 'Mapping folder as a virtual drive letter using subst'
date: '2007-09-26T23:49:44+02:00'
status: publish
permalink: /article/windows-subst-folder.html
author: Snakefoot
excerpt: 'Mount a file folder as a drive-letter, like a shortcut to make it easier to access the folder.'
type: post
id: 748
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - command-line-switches
    - drive-mount
    - subst
    - user-account-protection
post_format: []
tags:
    - 'drive-mount,subst,user-account-protection,command-line-switches'
---
It can be useful to map a very deep nested folder as a drive letter, so it is easier to access by Windows Explorer along with all other applications. The command line utility **subst.exe** provides this functionality:

> Subst x: C:\\Very\\Long\\Folder\\Path

 To free the assigned drive-letter again use the **subst** command like this:
 > Subst x: /D

 Note when restarting the computer then all mapped drive letters are forgotten. One can put the subst command into a startup-script which is [launched at startup](/article/windows-startup-order.html), so the mapping is done automatically again at user login.  
  
 Note the utility [Visual Subst](http://www.ntwind.com/software/utilities/visual-subst.html "	
NTWind Software") is a more GUI friendly utility for managing virtual drives created with subst (Has option to mount drives at boot / startup).   
  
 Note Windows Vista [User Account Protection](/article/winnt-user-account-protection.html) introduces a special behavior with Subst.exe as the drive-letter is only seen by the user-account that has performed the mapping. This means that when changing between regular user and elevated user then, one has to perform the subst command in both contexts.  
  
 Credits [SearchWinComputing.com](http://searchwincomputing.com/)