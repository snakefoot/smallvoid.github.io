---
title: 'NDIS 5 hardware features that increases network performance'
date: '2007-10-31T00:44:54+01:00'
status: publish
permalink: /article/winnt-ndis5-network-features.html
author: Snakefoot
excerpt: 'Windows can activate NDIS 5 network hardware features for offloading the system processor.'
type: post
id: 758
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - network-interface-card
    - network-performance
    - tcpip
    - tcpip-offload
post_format: []
tags:
    - 'tcpip-offload,network-performance,tcpip,network-interface-card'
---
Windows will detect if the network hardware has capabilities for offloading of the tasks required to maintain the TCP/IP stack.

- **TCP/IP checksum calculation** - Each packet sent needs a verification checksum, so the receiver knows that packet wasn't damaged during the transfer. This checksum can be calculated by the NIC.
- **TCP/IP segmentation** - Also known as TCP Large Send where Windows delivers a large message to the NIC and it is responsible for chopping up the message according to network [MTU](/article/tcpip-mtu-size.html). This feature is not enabled by default, and Microsoft sees this as an experimental feature.
- **Internet Protocol Security (IPSec) Encryption Ciphers and Message Digests** - Provides encryption of the packets sent/received at the hardware level.
 
 Checksum offloading should not be activated if one of the following features are turned on:
 - Windows Firewall
 
 Note to disable the offloading of processor tasks to the network adapter:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DisableTaskOffload = 1 (Default not set)  
>   
>  More Info [MS KB888750](http://support.microsoft.com/kb/888750 "Slow performance when you try to access resources on your Virtual Server 2005 host computer from a guest virtual machine")  
>  More Info [MS KB904946](http://support.microsoft.com/kb/904946 "You experience intermittent communication failure between computers that are running Windows XP or Windows Server 2003")  
>  More Info [MS KB936702](http://support.microsoft.com/kb/936702 "ISA 2006 clients are repeatedly prompted for credentials when they try to access Outlook Web Access")

 More Info [WHDC - NDIS 5.0 Overview](http://www.microsoft.com/whdc/archive/ndis5.mspx)  
 More Info [WHDC - Windows Network Task Offload](http://www.microsoft.com/whdc/device/network/taskoffload.mspx)  