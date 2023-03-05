---
title: 'Configure network file system aliasing'
date: '2005-06-23T22:47:06+02:00'
status: publish
permalink: /article/winnt-network-system-aliasing.html
author: Snakefoot
excerpt: 'Disabling system aliasing can free resources but will disable mounting and reparse points'
type: post
id: 448
category:
    - 'File Sharing'
tag:
    - network-share
    - system-aliasing
post_format: []
tags:
    - 'network-share,system-aliasing'
---
Aliasing is a feature that is included with Windows Server 2003. This feature lets multiple long file names or multiple short file names refer to the same file (Used for mounting- and reparse-points). Disabling file system aliasing can improve performance as it will increase the available cache size for the server service:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  NoAliasingOnFileSystem = 1 (Default = 0)  
>   
>  More Info [MS KB889588](http://support.microsoft.com/kb/889588 "How to optimize Office Access and Jet database engine network performance with Windows 2000-based and Windows XP-based clients [Q889588]")  
>  More Info [MS KB894372](http://support.microsoft.com/kb/894372 "Support for Windows Server 2003 SP1 on Windows Storage Server 2003-based server appliances [Q894372]")

 Credits [www.jsifaq.com](http://www.jsifaq.com/)