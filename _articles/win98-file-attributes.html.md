---
title: 'Show the file attributes column in Windows Explorer'
date: '2000-01-01T23:19:37+01:00'
permalink: /article/win98-file-attributes.html
author: Snakefoot
excerpt: 'Display the file attributes in the detail view of Windows Explorer for Windows 98 Second Edition.'
type: post
id: 168
categories:
    - windows-98_tips
tags:
    - desktop
    - windows-explorer
---
Windows 98 Second Edition (SE) doesn't include "Show File Attributes in Detail View" in the Folder Options (Windows 98 first edition does).  
  
 To add the column to the Windows Explorer update this registry key:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  ShowAttribCol = 1

 More Info <a href="https://www.bing.com/search?q=KB+241380+Q241380" rel="nofollow" title="'Show File Attributes in Detail View' Option Not Available in Windows 98 Second Edition [Q241380]">MS KB241380</a>