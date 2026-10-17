---
title: 'Clear Temporary Internet Files cache at exit'
date: '2002-11-12T00:35:00+01:00'
permalink: /article/ie-empty-temporary-internet-files.html
author: Snakefoot
excerpt: 'How to configure Internet Explorer, so it will empty its cache at program exit.'
type: post
id: 133
categories:
    - web-browser_internet-explorer-ie4
    - web-browser_internet-explorer-ie5
    - web-browser_internet-explorer-ie6
    - web-browser_internet-explorer-ie7
    - web-browser_internet-explorer-ie8
    - web-browser_internet-explorer-ie9
tags:
    - cache
    - cookies
    - privacy
    - temporary-internet-files
---
It can be useful to empty the [Temporary Internet Files](/article/ie-temporary-internet-files.html) cache if wanting to save space for roaming profiles, or if in an environment where one don't want other people to see what pages one have been visiting.  
  
 To configure this feature:

1. Start Internet Explorer
2. In the menu-item "Tools" select "Internet Options"
3. Select the "Advanced"-Tab
4. In the "Security" section tick "Empty Temporary Internet Files Folder When Browser Is Closed"
 
 This can also be done with this DWORD registry key :  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings \\Cache\]  
>  Persistent = 0 (Don't Clear= 1, Clear at exit = 0, Default = 1)

 Note this will not delete cookies created by sites visited and it will not empty history of visited pages.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20185255%20Q185255" rel="nofollow" title="How Not to Save Cached Internet Files with Roaming User Profiles [Q185255]">MS KB185255</a>  
  
 Note Internet Explorer 8/9/10 introduces the feature "Private Browsing", which automatically cleans up when stopping the browse session. It will make sure that no trace is left on the local machine, of the visited web pages (Including cookies and browsing history). You can start InPrivate Browsing from the [new tab page](/article/ie-about-tabs-rows.html) or the toolbar "Safety" button (CTRL+SHIFT+P).  
  
 Credits [regedit.com](http://www.regedit.com/)