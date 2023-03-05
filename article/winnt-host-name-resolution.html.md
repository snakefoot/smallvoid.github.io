---
title: 'Configure host name resolution order in Windows NT'
date: '2004-10-10T22:16:21+02:00'
status: publish
permalink: /article/winnt-host-name-resolution.html
author: Snakefoot
excerpt: 'Configure the priority of how it should lookup the physical network address of a computer.'
type: post
id: 219
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - dns
    - host-name
    - hosts-file
    - name-resolution
    - netbios
    - tcpip
    - wins
post_format: []
tags:
    - 'host-name,name-resolution,netbios,dns,wins,tcpip,hosts-file'
---
One can change the HOST resolution order for whether it should use NetBIOS or DNS first:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DnsNbtLookupOrder = 0 (0 = Use DNS first; 1 = Use NetBIOS first; Default = 0)  
>   
>  Note this option was made available with WinNT4 SP4.  
>   
>  More Info [MS KB171567](http://support.microsoft.com/kb/171567 "Windows NT 4.0 ServiceProvider Priority Values Not Applied [Q171567]")

 One can change how it should perform NetBIOS resolution (Nodetype):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Netbt \\Parameters\]  
>  NodeType = 1 (1= b-node; 2= p-node; 4= m-node; 8= h-node; Default=1 or 8 depending on WINS available)  
>   
>  More Info [MS KB142692](http://support.microsoft.com/kb/142692 "Minimizing WAN Traffic [Q142692]")  
>  More Info [MS KB160177](http://support.microsoft.com/kb/160177 "Default Node Type for Microsoft Clients [Q160177]")

 One can configure whether it should use DNS and HOSTS-file at all with this DWORD:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Netbt \\Parameters\]  
>  EnableDNS = 0 (Default = 1)

 Related [Description of Host Name Resolution Order](/article/windows-host-name-resolution.html)