---
title: 'Configure host name resolution order in Windows NT'
date: '2004-10-10T22:16:21+02:00'
permalink: /article/winnt-host-name-resolution.html
author: Snakefoot
excerpt: 'Configure the priority of how it should lookup the physical network address of a computer.'
type: post
id: 219
categories:
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - dns
    - host-name
    - hosts-file
    - name-resolution
    - netbios
    - tcpip
    - wins
---
One can change the HOST resolution order for whether it should use NetBIOS or DNS first:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DnsNbtLookupOrder = 0 (0 = Use DNS first; 1 = Use NetBIOS first; Default = 0)  
>   
>  Note this option was made available with WinNT4 SP4.  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+171567+Q171567" rel="nofollow" title="Windows NT 4.0 ServiceProvider Priority Values Not Applied [Q171567]">MS KB171567</a>

 One can change how it should perform NetBIOS resolution (Nodetype):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Netbt \\Parameters\]  
>  NodeType = 1 (1= b-node; 2= p-node; 4= m-node; 8= h-node; Default=1 or 8 depending on WINS available)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+142692+Q142692" rel="nofollow" title="Minimizing WAN Traffic [Q142692]">MS KB142692</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+160177+Q160177" rel="nofollow" title="Default Node Type for Microsoft Clients [Q160177]">MS KB160177</a>

 One can configure whether it should use DNS and HOSTS-file at all with this DWORD:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Netbt \\Parameters\]  
>  EnableDNS = 0 (Default = 1)

 Related [Description of Host Name Resolution Order](/article/windows-host-name-resolution.html)