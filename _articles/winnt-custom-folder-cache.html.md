---
title: 'Configure caching of remote customized folders'
date: '2005-11-16T20:32:46+01:00'
permalink: /article/winnt-custom-folder-cache.html
author: Snakefoot
excerpt: 'Enable caching of desktop.ini can improve the speed of browsing custom folders on remote computers.'
type: post
id: 405
categories:
    - windows-xp_file-sharing
tags:
    - custom-folders
---
It is possible to speed up browsing of remote shared folders, which have been [customized](/article/winnt-custom-folder.html). It is done by enabling caching of the desktop.ini.

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\policies \\Explorer\]  
>  UseDesktopIniCache = 1 (Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20840309%20Q840309" rel="nofollow" title="Browsing the My Documents folder on a network share with Windows Explorer from a Windows XP-based computer takes longer than expected [Q840309]">MS KB840309</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20883791%20Q883791" rel="nofollow" title="Explorer.exe repeatedly quits unexpectedly in Windows XP [Q883791]">MS KB883791</a>

 Note if having placed the "My Documents" on a remote share, and have enabled caching of the desktop.ini, then it might give slow performance, because a bug in the cache process makes it cache the entire contents of the "My Documents" folder. More Info <a href="https://www.bing.com/search?q=KB%20898612%20Q898612" rel="nofollow" title="You may experience slow performance in Windows XP SP2 when you use the Favorites menu in Internet Explorer or in Windows Explorer [Q898612]">MS KB898612</a>  