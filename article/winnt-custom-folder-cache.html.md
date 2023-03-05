---
title: 'Configure caching of remote customized folders'
date: '2005-11-16T20:32:46+01:00'
status: publish
permalink: /article/winnt-custom-folder-cache.html
author: Snakefoot
excerpt: 'Enable caching of desktop.ini can improve the speed of browsing custom folders on remote computers.'
type: post
id: 405
category:
    - 'File Sharing'
tag:
    - custom-folders
post_format: []
tags:
    - custom-folders
---
It is possible to speed up browsing of remote shared folders, which have been [customized](/article/winnt-custom-folder.html). It is done by enabling caching of the desktop.ini.

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\policies \\Explorer\]  
>  UseDesktopIniCache = 1 (Default = 0)  
>   
>  More Info [MS KB840309](http://support.microsoft.com/kb/840309 "Browsing the My Documents folder on a network share with Windows Explorer from a Windows XP-based computer takes longer than expected [Q840309]")  
>  More Info [MS KB883791](http://support.microsoft.com/kb/883791 "Explorer.exe repeatedly quits unexpectedly in Windows XP [Q883791]")

 Note if having placed the "My Documents" on a remote share, and have enabled caching of the desktop.ini, then it might give slow performance, because a bug in the cache process makes it cache the entire contents of the "My Documents" folder. More Info [MS KB898612](http://support.microsoft.com/kb/898612 "You may experience slow performance in Windows XP SP2 when you use the Favorites menu in Internet Explorer or in Windows Explorer [Q898612]")  