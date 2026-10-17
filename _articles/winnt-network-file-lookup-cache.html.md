---
title: 'Configure lookup caching of files placed on network shares'
date: '2005-06-23T22:40:27+02:00'
permalink: /article/winnt-network-file-lookup-cache.html
author: Snakefoot
excerpt: 'The lookup cache for network files makes it faster to reopen a file placed on a remote share.'
type: post
id: 447
categories:
    - windows-2003_file-sharing
    - windows-xp_file-sharing
    - windows-2000_file-sharing
tags:
    - file-cache
    - network-performance
    - network-share
---
When requesting a file on the network, the request is handled by the [MUP](/article/winnt-network-priority.html), and depending on configuration, then the request is passed to the Microsoft Network SMB Redirector (MrxSmb).  
 The SMB Redirector keeps a cache of recent accessed files, but by default it only caches short-filenames. If frequently accessing the same network files (Like ex. a database), then performance can be improved by using 8.3 short-filenames. Another solution is to configure the SMB redirector to cache long-filenames.

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\MRxSmb \\Parameters\]  
>  InfoCacheLevel = 16 (Default = 1, Disabled = 0, Both Long &amp; Short = 16)  
>   
>  Note WinXP requires SP2 to recognize this registry-key. More Info <a href="https://www.bing.com/search?q=KB%20834350%20Q834350" rel="nofollow" title="Your access to network resources is slower in Windows XP than in earlier versions of Windows [Q834350]">MS KB834350</a>  
>   
>  Note Win2k requires a post SP4 hotfix (Included in the Update Rollup) from Microsoft to recognize this registry-key. More Info <a href="https://www.bing.com/search?q=KB%20843418%20Q843418" rel="nofollow" title="You may experience decreased performance when you access network resources or when you use Microsoft Access in Windows 2000 [Q843418]">MS KB843418</a>

 Note there is a limit for how many file handles the client redirector will keep it in its cache:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  DormantFileLimit = 45 (Default = 45)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20890584%20Q890584" rel="nofollow" title="TOO_MANY_OPEN_FILES error message when the redirector component in Windows Server 2003 uses the SMB protocol to open a file in a shared network folder [Q890584]">MS KB890584</a>

 Note the client redirector has a scavenger thread, which cleans old file handles from its cache. One can configure how often it should look for old handles to remove (WinXP/Win2k3):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanWorkstation \\Parameters\]  
>  ScavengerTimeLimit = 30 (Default = Every 10 secs, Min = 10 secs, Max = 120 secs)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20816073%20Q816073" rel="nofollow" title="Compile on a Windows XP-based computer takes longer to complete than on a Windows NT-based computer [Q816073]">MS KB816073</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20890553%20Q890553" rel="nofollow" title="You may experience delays of between 10 and 60 seconds when you use UNC paths to access files that are stored on a remote SMB server on a multihomed Windows Server 2003-based computer [Q890553]">MS KB890553</a>

 Credits [www.jsifaq.com](http://www.jsifaq.com/)