---
title: 'Disable search history for Windows Explorer in Windows 7'
date: '2009-08-29T00:57:50+02:00'
status: publish
permalink: /article/winnt-explorer-search-history.html
author: Snakefoot
excerpt: 'Stop auto suggestion of recent file searches in the Windows Explorer search box.'
type: post
id: 790
category:
    - Desktop
tag:
    - file-search
    - windows-explorer
post_format: []
tags:
    - 'windows-explorer,file-search'
---
Windows Explorer in Windows 7 will remember your previous file searches. When typing in a new search, then it will perform auto-suggest using the previous searches.  
  
 It is possible to clear a previous file search by hovering over the suggestion in the search-box, and pressing the delete-key.  
  
 Turn off the search history feature by setting this DWORD value:

> \[HKEY\_CURRENT\_USER \\Software \\Policies \\Microsoft \\Windows \\Explorer\]  
>  DisableSearchBoxSuggestions = 1  
>   
>  This should match the group policy "Turn off display of recent search entries in the Windows Explorer search box" (User Configuration | Administrative Templates | Windows Components | Windows Explorer)

 Clear all cached search history entries by deleting the WordWheelQuery branch:
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\WordWheelQuery\]

 Credits [WinHelpOnline](http://www.winhelponline.com/blog/disable-explorer-search-box-suggestions-windows-7/)