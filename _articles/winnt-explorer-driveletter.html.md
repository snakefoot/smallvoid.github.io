---
title: 'Change the display of drive-letters in Windows Explorer'
date: '2006-03-16T21:46:18+01:00'
permalink: /article/winnt-explorer-driveletter.html
author: Snakefoot
excerpt: 'Control in what order the drive letter and label should be shown in My Computer.'
type: post
id: 414
categories:
    - windows-xp_tips
    - windows-2000_tips
    - windows-2003_tips
    - windows-vista_tips
tags:
    - desktop
    - visual-style
    - windows-explorer
---
My Computer displays by default the drive-letters like this (Where "System" is the partition label):

> System (C:)  
>  Compact Disc (Z:)

 It is possible to change this the position of the drive letter, so it is in front:
 > (C:) System  
 > (Z:) Compact Disc

 This is done with this registry key:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  ShowDriveLettersFirst = 4 (0 = Default)  
>   
>  1 = Drive letter first for remote drives  
>  2 = No drive letters (Same as "Show drive letters" in Vista Folder Options)  
>  4 = Drive letter first for all drives  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20330193%20Q330193" rel="nofollow" title="The computer description appears before the computer name in Windows XP [Q330193]">MS KB330193</a>

 Credits [Windowsxp.mvps.org](http://windowsxp.mvps.org/)