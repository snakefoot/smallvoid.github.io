---
title: 'Configure network file system aliasing'
date: '2005-06-23T22:47:06+02:00'
permalink: /article/winnt-network-system-aliasing.html
author: Snakefoot
excerpt: 'Disabling system aliasing can free resources but will disable mounting and reparse points'
type: post
id: 448
categories:
    - windows-2003_file-sharing
tags:
    - network-share
    - system-aliasing
---
Aliasing is a feature that is included with Windows Server 2003. This feature lets multiple long file names or multiple short file names refer to the same file (Used for mounting- and reparse-points). Disabling file system aliasing can improve performance as it will increase the available cache size for the server service:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  NoAliasingOnFileSystem = 1 (Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20889588%20Q889588" rel="nofollow" title="How to optimize Office Access and Jet database engine network performance with Windows 2000-based and Windows XP-based clients [Q889588]">MS KB889588</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20894372%20Q894372" rel="nofollow" title="Support for Windows Server 2003 SP1 on Windows Storage Server 2003-based server appliances [Q894372]">MS KB894372</a>

 Credits [www.jsifaq.com](http://www.jsifaq.com/)