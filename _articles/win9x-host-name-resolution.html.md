---
title: 'Configure host name resolution order in Windows 9x'
date: '2004-10-10T21:41:48+02:00'
permalink: /article/win9x-host-name-resolution.html
author: Snakefoot
excerpt: 'Configure the priority of how it should lookup the physical network address of a computer.'
type: post
id: 216
categories:
    - windows-95_network
    - windows-98_network
    - windows-me_network
tags:
    - dns
    - hosts-file
    - name-resolution
    - netbios
    - wins
---
One can change the HOST resolution order for whether it should use NetBIOS or DNS first:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
>  DnsNbtLookupOrder = 0 (0 = Use DNS first; 1 = Use NetBIOS first; Default = 0)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+216470+Q216470" rel="nofollow" title="Windows Sockets 2.0 Does Not Use DnsNbtLookupOrder Value [Q216470]">MS KB216470</a>

One can change how it should perform NetBIOS resolution (Nodetype):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  NodeType = 1 (1= b-node; 2= p-node; 4= m-node; 8= h-node; Default=1 or 8 depending on WINS available)  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB+160177+Q160177" rel="nofollow" title="Default Node Type for Microsoft Clients [Q160177]">MS KB160177</a>

One can configure whether it should use DNS and HOSTS-file at all:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  EnableDNS = "0" (Default = "1")  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB+137368+Q137368" rel="nofollow" title="How to Disable NetBIOS Name Resolution on DNS [Q137368]">MS KB137368</a>

Note in Win95 without Winsock 2.0 applied one can configure name resolution order with these BINARY keys:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\MSTCP \\ServiceProvider\]  
 >  LocalPriority = 0xF3 (Range -32768 to 32767; Lower value means higher priority)  
 >  HostsPriority = 0x1F (Range -32768 to 32767; Lower value means higher priority)  
 >  DnsPriority = 0x7D0 (Range -32768 to 32767; Lower value means higher priority)  
 >  NetbtPriority = 0x7D1 (Range -32768 to 32767; Lower value means higher priority)  
 >   
 >  More Info <a href="https://www.bing.com/search?q=KB+139270+Q139270" rel="nofollow" title="How to Change Name Resolution Order on Windows 95 and Windows NT [Q139270]">MS KB139270</a>  
 >  More Info <a href="https://www.bing.com/search?q=KB+170619+Q170619" rel="nofollow" title="Windows 95 ServiceProvider Priority Values Not Applied [Q170619]">MS KB170619</a>  
 >  More Info <a href="https://www.bing.com/search?q=KB+250662+Q250662" rel="nofollow" title="Description of the TCP/IP Registry Entries in the MSTCP\ServiceProvider Subkey [Q250662]">MS KB250662</a>

 Related [Description of Host Name Resolution Order](/article/windows-host-name-resolution.html)