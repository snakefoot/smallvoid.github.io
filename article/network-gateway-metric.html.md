---
title: 'Using router metric to specify primary gateway'
date: '2002-01-23T21:50:03+01:00'
status: publish
permalink: /article/network-gateway-metric.html
author: Snakefoot
excerpt: 'Description of how router metric works, and how to use it to prioritise gateways and perform simple load balancing.'
type: post
id: 201
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - automatic-metric
    - default-gateway
    - lan
    - network-load-balancing
    - tcpip
    - wan
post_format: []
tags:
    - 'default-gateway,automatic-metric,network-load-balancing,tcpip,lan,wan'
---
If you are able to connect to several gateways/routers to other networks, it is possible to prioritize in which order the gateways should be searched for a certain address.  
  
 This is done by the Metric setting which is assigned to each gateway. The gateway with lowest Metric is the first to be searched(Default Gateway). Metric is the cost of using that gateway, and it will always use the one with the lowest cost first.  
  
 The metric can also be applied when having more than one network adapter, which connects to the same Network(Subnet). Example if using a wireless NIC and a standard NIC, then one can decide if it should use go through the Wireless NIC before using the Standard NIC. This is done by lowering the interface metric of the Wireless NIC.  
  
 The metric can also be used for manual load balancing between multiple network adapters:

- Install TCP/IP for all adapters and assign them a different IP-address on the same subnet (Becomes Multihoming)
- If a certain adapter should be dedicated for outgoing traffic then it should be given a lower interface metric
- If a certain adapter should be used for certain incoming traffic then make sure the clients connects to its IP-Address 
  - Note Netbios traffic (outgoing/incoming) can only be handled by a single adapter or else a name conflict will arise (Though it doesn't have to be the one dedicated for outgoing IP traffic)
  - Note it is possible for clients to connect to a service (FTP/HTTP,etc.) through all network adapters (To force clients to use a certain adapter one can use DNS or port blocking)
 
 To configure the metric in Win2k/WinXP (WinNT4/Win9x can use the command "route"):
1. Open **Control Panel**
2. Double click **Network and Dial-up Connections**(Win2k) or **Network Connections**(WinXP)
3. Righ click **Local Area Connection** and select **Properties**
4. Double click **Internet Protocol (TCP/IP)**
5. Press **Advanced**-button and it is possible to configure gateways and interface metric
 
 Note Automatic Metric is a new feature in WinXP, which automatically assign a metric value according to interface bandwidth (Not latency), the higher bandwidth the lower the metric. More Info [MS KB299540](http://support.microsoft.com/kb/299540 "An Explanation of the Automatic Metric Feature for Internet Protocol Routes [Q299540]")  
  
 Note if two network interfaces have the same metric value, then their priority is based on the network binding order. To configure the network binding order in Win2k/WinXP:
1. Open **Control Panel**
2. Double click **Network and Dial-Up Connections**
3. In the menu select **Advanced** and select **Advanced Settings...**
  - Vista/Win7 will only display the Advanced menu-item when pressing the ALT-key. More Info [MS KB2526067](http://support.microsoft.com/kb/2526067 "How to change the network connection priority in Windows 7 [Q299540/KB299540]").
4. Select the **Adapter and Bindings**-tab and change the priority of the network **Connections**.
 
 More Info [MS KB140859](http://support.microsoft.com/kb/140859 "TCP/IP Routing Basics for Windows NT [Q140859]")  
 More Info [MS KB164214](http://support.microsoft.com/kb/164214 "Distance Vector Routing Basics [Q164214]")  
 More Info [MS KB894564](http://support.microsoft.com/kb/894564 "How to change the binding order of network adapters in Windows XP and in Windows 2000 [Q894564]")  
 More Info [Cable Guy - Default Gateway Behavior for TCP/IP](http://www.microsoft.com/technet/community/columns/cableguy/cg0903.mspx "September 2003 - Default Gateway Behavior for Windows TCP/IP")  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)