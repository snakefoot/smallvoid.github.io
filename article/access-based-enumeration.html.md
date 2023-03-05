---
title: 'Access-based Enumeration'
date: '2006-02-18T02:33:21+01:00'
status: publish
permalink: /article/access-based-enumeration.html
author: Snakefoot
excerpt: 'Windows 2003 addon which hides folders within a share, that the user cannot access anyway.'
type: post
id: 151
category:
    - Utilities
tag:
    - access-control-list
    - ntfs
post_format: []
tags:
    - 'access-control-list,ntfs'
---
Windows 2003 Service Pack 1 includes a new feature called Access-based Enumeration. When making a file share one can use this feature to specify that it should only list files the user has [permission to access](/article/ntfs-access-control.html). Instead of listing all files and folders and give the user access denied message, when the user tries to access a file/folder without the proper permissions.  
  
 Download [Access-based Enumeration](http://go.microsoft.com/fwlink/?LinkId=46228)  
  
 More Info [MS KB303758](http://support.microsoft.com/kb/303758 "You cannot configure NTFS permissions to hide files or folders from unauthorized users [Q303758]")