---
title: 'Configure notification events received from mapped network shares'
date: '2003-10-04T21:36:59+02:00'
permalink: /article/winnt-network-notification.html
author: Snakefoot
excerpt: 'Windows Explorer sends a Change Notification request to the remote server when mapping a network share.'
type: post
id: 443
categories:
    - windows-2003_file-sharing
    - windows-xp_file-sharing
    - windows-2000_file-sharing
tags:
    - network-performance
    - network-share
---
When mapping a network share as a network drive, then Windows Explorer tells the remote server, that it should be notified by any changes made on the network share. If a file changes on the network share, then each Workstation registered as having that shared mapped as a network drive will get a SMB notification about the change. If many users are updating files on the network share, then it will cause a lot of traffic (bad for slow connections like VPN or dialup) and can make the tree-view in the File Explorer flicker.  
  
 To configure whether Windows Explorer should register for events happening on the mapped network share:

> \[HKEY\_CURRENT\_USER \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoRemoteChangeNotify = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+812669+Q812669" rel="nofollow" title="An update is available in Windows to turn off directory notification SMB requests [Q812669]">MS KB812669</a>

 Windows XP and Windows 2003 extends the event registering from just being the root-folder, to actually be all underlying sub-folders and their files (Even more traffic). To change this back to only register for events happening in the root of the mapped network share:
> \[HKEY\_CURRENT\_USER \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoRemoteRecursiveEvents = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+330929+Q330929" rel="nofollow" title="Windows XP May Cause Extra SMB Notify Change Traffic [Q330929]">MS KB330929</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+816375+Q816375" rel="nofollow" title="Windows XP Explorer Pane Flickers on Mapped Network Drives [Q816375]">MS KB816375</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+885189+Q885189" rel="nofollow" title="Slow performance when you use a mapped drive to copy files to a remote server from a Windows Server 2003-based computer [Q885189]">MS KB885189</a>

 Note if using software which relies on being notified of file changes and its files are placed on a mapped network share, then this change in policy might give unpredictable results.  
  
 Note only WinXP SP2+ reacts to the registry entries above, or if having applied the <a href="https://www.bing.com/search?q=KB+810565+Q810565" title="Hyperlinks open in Internet Explorer instead of in default browser or Help and Support Center [Q810565]" rel="nofollow">Critical Update - MS KB810565</a>.  
  
 More Info <a href="https://www.bing.com/search?q=KB+831129+Q831129" rel="nofollow" title="Folder tree flickers when you view a mapped network drive in Microsoft Windows Explorer [Q831129]">MS KB831129</a>  