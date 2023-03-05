---
title: 'Configure host name resolution order in Windows 9x'
date: '2004-10-10T21:41:48+02:00'
status: publish
permalink: /article/win9x-host-name-resolution.html
author: Snakefoot
excerpt: 'Configure the priority of how it should lookup the physical network address of a computer.'
type: post
id: 216
category:
    - Network
    - Network
    - Network
tag:
    - dns
    - hosts-file
    - name-resolution
    - netbios
    - wins
post_format: []
tags:
    - 'hosts-file,name-resolution,netbios,dns,wins'
---
One can change the HOST resolution order for whether it should use NetBIOS or DNS first:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
>  DnsNbtLookupOrder = 0 (0 = Use DNS first; 1 = Use NetBIOS first; Default = 0)  
>   
>  More Info [MS KB216470](http://support.microsoft.com/kb/216470 "Windows Sockets 2.0 Does Not Use DnsNbtLookupOrder Value [Q216470]")

One can change how it should perform NetBIOS resolution (Nodetype):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  NodeType = 1 (1= b-node; 2= p-node; 4= m-node; 8= h-node; Default=1 or 8 depending on WINS available)  
 >   
 >  More Info [MS KB160177](http://support.microsoft.com/kb/160177 "Default Node Type for Microsoft Clients [Q160177]")

One can configure whether it should use DNS and HOSTS-file at all:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  EnableDNS = "0" (Default = "1")  
 >   
 >  More Info [MS KB137368](http://support.microsoft.com/kb/137368 "How to Disable NetBIOS Name Resolution on DNS [Q137368]")

Note in Win95 without Winsock 2.0 applied one can configure name resolution order with these BINARY keys:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\MSTCP \\ServiceProvider\]  
 >  LocalPriority = 0xF3 (Range -32768 to 32767; Lower value means higher priority)  
 >  HostsPriority = 0x1F (Range -32768 to 32767; Lower value means higher priority)  
 >  DnsPriority = 0x7D0 (Range -32768 to 32767; Lower value means higher priority)  
 >  NetbtPriority = 0x7D1 (Range -32768 to 32767; Lower value means higher priority)  
 >   
 >  More Info [MS KB139270](http://support.microsoft.com/kb/139270 "How to Change Name Resolution Order on Windows 95 and Windows NT [Q139270]")  
 >  More Info [MS KB170619](http://support.microsoft.com/kb/170619 "Windows 95 ServiceProvider Priority Values Not Applied [Q170619]")  
 >  More Info [MS KB250662](http://support.microsoft.com/kb/250662 "Description of the TCP/IP Registry Entries in the MSTCP\ServiceProvider Subkey [Q250662]")

 Related [Description of Host Name Resolution Order](/article/windows-host-name-resolution.html)