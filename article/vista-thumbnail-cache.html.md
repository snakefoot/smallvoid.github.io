---
title: 'Configure the thumbnail cache for picture preview'
date: '2007-09-17T22:41:15+02:00'
status: publish
permalink: /article/vista-thumbnail-cache.html
author: Snakefoot
excerpt: 'The thumbnail cache allows the Windows Explorer to show preview of pictures, but also makes the browsing slower.'
type: post
id: 745
category:
    - Desktop
tag:
    - custom-folders
    - thumbnail-cache
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,custom-folders,thumbnail-cache'
---
Windows Vista changes how cached thumb nails are stored. Instead of having [Thumbs.db files](/article/windows-thumbnail-cache.html) shattered all over the hard disk, then a central database is used instead, which is located here (files are prefixed thumbcache\_????.db):

> C:\\Users\\ {User Account Name} \\AppData \\Local \\Microsoft \\Windows \\Explorer

 Note to clear the the thumbnail cache, one can use the [Disk Cleanup wizard](http://windowshelp.microsoft.com/Windows/en-US/Help/1264bc24-72a8-48aa-84e3-a355327139d91033.mspx).  
  
 Note to disable the use of the thumbnail cache:
1. Click on the **Start** menu and choose **Computer**.
2. In the **Tools** menu click **Folder options...**.
3. Select the **View** fan and find and tick the option **Always show icons, never thumbnails**.
 
 Credits [My Digital Life](http://www.mydigitallife.info/)