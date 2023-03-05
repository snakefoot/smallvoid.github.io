---
title: 'Configure shortcut link tracking'
date: '2002-03-16T12:39:37+01:00'
status: publish
permalink: /article/winnt-shortcut-link-tracking.html
author: Snakefoot
excerpt: 'Control what should happen when a shortcut is detected as being broken.'
type: post
id: 32
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - link-shortcut
    - link-tracking
    - ntfs
post_format: []
tags:
    - 'ntfs,link-shortcut,link-tracking'
---
A shortcut contains the location of the target file, if the target file cannot be found when using the shortcut, then Win2k/WinXP automatically tries to find the target file and update the shortcut with the new file-location (If it finds the file).  
  
 There are several methods used for tracking the target-file:

1. It searches all paths that are included in the shortcut, and if the file is placed on a NTFS partition, then it will also try to use the file ID to find the new path of the file. > \[HKEY\_CURRENT\_USER \\Software \\Microsoft Windows \\CurrentVersion \\Policies \\Explorer\]  
  >  NoResolveTrack = 0 (Disable Tracking Completely = 1, Default = 0)  
  >   
  >  More Info [MS KB299780](http://support.microsoft.com/kb/299780 "HOW TO: Disable the NTFS File System Tracking of Broken Shortcut Links [Q299780]")
2. If tracking isn't completely disabled and the above step didn't work, then it performs a comprehensive search of the target drive to resolve the shortcut. This can take time and will cause a lot of disk activity. > \[HKEY\_CURRENT\_USER \\Software \\Microsoft Windows \\CurrentVersion \\Policies \\Explorer\]  
  >  NoResolveSearch = 1 (Default = 0)  
  >   
  >  More Info [MS KB292504](http://support.microsoft.com/kb/292504 "Policy Settings for the Start Menu in Windows XP [Q292504]")
3. If the above methods doesn't work, and the shortcut was original created on another computer, then it will try to access the other computer to find the target file. This can take time and will cause a lot of network traffic. > \[HKEY\_CURRENT\_USER \\Software \\Microsoft Windows \\CurrentVersion \\Policies \\Explorer\]  
  >  LinkResolveIgnoreLinkInfo = 1 (Default = 0)  
  >   
  >  Note when using a shortcut in Windows NT4, which originally came from another computer, then it will always try to use the target file on the other computer even if having the file placed locally.  
  >   
  >  More Info [MS KB150215](http://support.microsoft.com/kb/150215 "Disabling Automatic Network Shortcut Resolution [Q150215]")  
  >  More Info [MS KB158682](http://support.microsoft.com/kb/158682 "Shortcuts Created Under Windows NT 4.0 Resolve to UNC Paths [Q158682]")
 
 Credits [ntcanuck.com](http://ntcanuck.com/)