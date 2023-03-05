---
title: 'Load balancing over several Network Adapters'
date: '2000-01-01T23:59:48+01:00'
status: publish
permalink: /article/winnt-network-load.html
author: Snakefoot
excerpt: 'Configure how the TCP/IP should respond when multiple network adapters are installed.'
type: post
id: 426
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - network-interface-card
    - network-load-balancing
    - tcpip
    - wins
post_format: []
tags:
    - 'network-load-balancing,tcpip,wins,network-interface-card'
---
It is possible to have the OS to balance the network load for the computer when having several Network Adapters.  
  
 This is controlled by these DWORD values :

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NetBT \\Parameters\]  
>  RandomAdapter = 1 (Disabled = 0, Enabled = 1, Default = 0)  
>  SingleResponse = 1 (Send All = 0, Send One = 1, Default = 0)

 The RandomAdapter specifies whether it should respond back with a random IP-Address (One for each adapter), or if it should respond back with the IP Address for the adapter the request was received from.  
  
 The SingleResponse says that it should only send one IP address when WINS does a name query request.  
  
 More Info [MS KB131736](http://support.microsoft.com/kb/131736 "TCP/IP: Load Balancing vs. Distributed Network Sessions [Q131736]")  
 More Info [MS KB175767](http://support.microsoft.com/kb/175767 "Expected Behavior of Multiple Adapters on Same Network [Q175767]")  
  
 Note there is also a technology called [Windows NT Load Balancing Service (WLBS - NT4)](http://support.microsoft.com/kb/232997 "Convergence in Windows NT Load Balancing Service [Q232997]") or [Network Load Balancing (NBL - Win2k+)](http://support.microsoft.com/kb/240997 "Configuring Network Load Balancing [Q240997]"), which handles clustering of several machines to act like a single unit. The cluster of several machines can provide redundancy for critical applications and higher load handling. The above registry settings does not have anything to do with this kind of service.  
  
 Note not all applications supports that the underlying TCP/IP layer responds with random IP-addresses. Instead one can try to setup [Manual load balancing using metric](/article/network-gateway-metric.html).  
  
 Note hardware solutions (Ex. from Intel) for network load balancing also exists where several NIC's are bound together (Also called "teaming"/"trunking"/"grouping"), to team together as a single NIC using only one IP-Address.  
  
 Credits [regedit.com](http://regedit.com/)  