---
title: 'Configure TCPIP max transfer unit size in Windows 9x'
date: '2001-01-01T15:57:39+01:00'
permalink: /article/win9x-tcpip-mtu.html
author: Snakefoot
excerpt: 'Description of the registry keys used for configuring the TCP/IP max transfer unit (MTU) size in Windows 95 / 98 / Me.'
type: post
id: 191
categories:
    - windows-95_network
    - windows-98_network
    - windows-me_network
tags:
    - dialup-modem
    - lan
    - max-transfer-unit
    - network-performance
    - tcpip
    - wan
---
To change the MTU for an adapter :

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Class \\NetTrans \\{Adapter-Id}\]  
>  MaxMTU = "576"

 The {Adapter-Id} can have the value 0000, 0001, 000n. If several {Adapter-Id}, then find the correct one using the following ways:
- Looking at the value "DriverDesc" for each {Adapter-Id}, and see if it matches the wanted device (Ex. if modem then "Dialup Adapter")
- Change the TCP/IP setting for the adapter in network properties, example the DNS address. Then find the {Adapter-Id} which has that certain DNS-address
 
 More Info <a href="https://www.bing.com/search?q=KB%20250663%20Q250663" rel="nofollow" title="Description of the TCP/IP Registry Entries in the NetTrans Subkey [Q250663]">MS KB250663</a>  
  
 Note with <a href="https://www.bing.com/search?q=KB+285189+Q285189" title="Dial-Up Networking 1.4 Upgrade Is Available [Q285189]" rel="nofollow">DUN 1.3+</a> (Windows 98 and Windows Me has it installed by default) it is possible to set the MTU for a dialup adapter, without going into the registry. Control Panel -&gt; Network -&gt; Dial-Up Adapter -&gt; Advanced tab -&gt; IP Packet Size. - Automatic = 0 (576 bytes when below 128 kbps else 1500 bytes)
- Large = 1500 bytes
- Medium = 1000 bytes
- Small = 576 bytes
- Custom (Cannot set MTU below 576 bytes, without using registry editor)
 
 It is possible to change the values for the predefined "IP Packet Size" :
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Class \\Net \\{Dialup-Adapter-Id} \\Ndi \\params \\IPMTU \\enum\]  
 >  "1492"="Automatic"

 More Info <a href="https://www.bing.com/search?q=KB%20183437%20Q183437" rel="nofollow" title="Description of the Internet Protocol Packet Size Setting [Q183437]">MS KB183437</a>  
  
 Related [Finding the optimal TCPIP max transfer unit (MTU) size](/article/tcpip-mtu-size.html)  