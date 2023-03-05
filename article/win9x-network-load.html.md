---
title: 'Load balancing over several Network Adapters in Windows 9x'
date: '2002-10-12T21:32:10+02:00'
status: publish
permalink: /article/win9x-network-load.html
author: Snakefoot
excerpt: 'Configure how the TCP/IP should respond when multiple network adapters are installed.'
type: post
id: 200
category:
    - Network
    - Network
    - Network
tag:
    - network-interface-card
    - network-load-balancing
    - tcpip
post_format: []
tags:
    - 'network-load-balancing,tcpip,network-interface-card'
---
It is possible to have the OS to balance the network load for the computer when having several Network Adapters.  
  
 This is controlled by these STRING values:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
>  RandomAdapter = "1" (Disabled = "0", Enabled = "1", Default = "0")  
>  SingleResponse = "1" (Send All = "0", Send One = "1", Default = "0")

 The RandomAdapter specifies whether it should respond back with a random IP-Address (One for each adapter), or it should respond back with the IP Address for the adapter the request was received from.  
  
 The SingleResponse says that it should only send one IP address when WINS does a name query request.  
  
 Note if using Windows 95 without having installed Winsock2, then the registry values should be DWORD instead of STRING. Windows 98 / Me has Winsock2 installed by default.  
  
 Note not all applications supports that the underlying TCP/IP layer responds with random IP-addresses. Instead one can try to setup [Manual load balancing using metric](/article/network-gateway-metric.html).