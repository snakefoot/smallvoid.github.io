---
title: 'Automatically turn off screensaver when doing defrag'
date: '2002-10-12T00:41:38+02:00'
permalink: /article/win9x-screensaver-defrag.html
author: Snakefoot
excerpt: 'Keep the screensaver from starting when doing file defragmentation.'
type: post
id: 161
categories:
    - windows-98_tips
    - windows-me_tips
tags:
    - defrag
    - screensaver
---
If the Screensaver starts running while performing a defrag of a HDD partition then the defrag will take forever.  
 So if one has fallen in love with the screensaver, but don't want the hazzle of turning it off before starting a defrag, then this can be a help.  
  
 Update the following STRING values :

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Applets \\Defrag \\Settings\]  
>  (Default) = "YES"  
>  DisableScreenSaver = ""

 Note the screensaver will not be disabled if the Defrag is run as a scheduled task.  
  
 Also Read [Defrag partitions to speed up file access](/article/defrag-hard-disk-partition.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+229057+Q229057" rel="nofollow" title="Correct Instructions for Disabling Screen Saver During Defrag.exe [Q229057]">MS KB229057</a>  