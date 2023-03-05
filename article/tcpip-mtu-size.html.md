---
title: 'Finding the optimal TCPIP max transfer unit size'
date: '2001-01-01T13:15:05+01:00'
status: publish
permalink: /article/tcpip-mtu-size.html
author: Snakefoot
excerpt: 'Using PING to test the network connection and finding the best TCP/IP max transfer unit (MTU).'
type: post
id: 189
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - lan
    - max-transfer-unit
    - network-performance
    - ping
    - wan
post_format: []
tags:
    - 'max-transfer-unit,lan,wan,ping,network-performance'
---
When using a network, one is sending and receiving packets. On large networks like the Internet, which is a collection of small networks, the packets is passing through routers, which connects these small networks together.  
  
 The packet size, determines how much data is send for each packet. Each machine/router connected to the Internet is configured to accept a certain Max Transfer Unit (MTU). If the machine receives a packet which is larger than its MTU, then it tries to chop the packet up in smaller packets, or just drops the packet.  
  
 The MTU size for the connection is dependent on the machines/routers, that the packet has to travel through to reach destination. The lowest MTU of these machines/routers will set the limit for the MTU for the connection.

- If the MTU size is too small on your machine, then the connection will spend more time on sending headers than the actual data.
- If the MTU size is too large on your machine, then the connection will fragment the packets or there will not be any connection at all.
 
 The PING (Packet InterNet Groper) tool can be told to sent packets with a certain size to a certain destination address. The PING tool also has an option of disallowing the machines/routers in between the origin and destination to chop/fragment the packets. So if the packets are too large to handle, it will cause the machine/router to fail handling the packets. This allows us to use the PING tool to find the MTU for a certain connection.  
> PING &lt;IP-Address&gt; -f -l &lt;Packet-size-28&gt;

 Note that the usual minimum Internet standard packet size used is 576 and the usual maximum is 1500. When testing with the PING tool one have to subtract 28 from the packet size being tested. This is because the PING tool itself adds an IP Header (20 Bytes) and an ICMP-Header (8 Bytes), which together has the size of 28 bytes.  
  
 To test the MTU size of a connection to a machine/router, one pings the IP-Address of the machine/router with different Packet-Sizes. This is done until you find the packet size which is one byte too large for the machine/router(Along with with machines/routers in between) to handle.  
- If using network adapter and want to test, ping your own ip address. Ex.
  > PING 192.168.0.2 -f -l 1472
- If using router and want to test, ping router ip (Default Gateway) address. Ex.
  > PING 192.168.0.1 -f -l 1472
- To test your ISP, ping ISP's homepage address. Ex.
  > PING www.tiscali.dk -f -l 1472
- To test favorite homepage, ping the homepage address. Ex.
  > PING www.google.com -f -l 1472
 
 To configure the MTU in Windows: - [Windows 2000, XP, 2003, Vista using registry](/article/winnt-tcpip-mtu.html) or [Windows Vista using Netsh](/article/vista-tcpip-mtu.html)
- [Windows 95, 98, Me using Registry](/article/win9x-tcpip-mtu.html)
- [Windows NT4 using Registry](/article/winnt4-tcpip-mtu.html)
 
 Note different network types will enforce different MTU sizes:  
  
<table border="1"><tr><th>Network Type</th><th>MTU (bytes)</th><th>Details</th></tr><tr><td>Ethernet</td><td>1500</td><td> </td></tr><tr><td>IEEE 802.3/802.2</td><td>1492</td><td> </td></tr><tr><td>PPPoE</td><td>1492</td><td>Optimal MTU for PPPoE over ATM is 1454</td></tr><tr><td>X.25</td><td>576</td><td>Dialup Connection</td></tr><tr><td>Ethernet (Jumbo)</td><td>&gt;=9000</td><td>Gigabit networking</td></tr></table>

  
 Note [VPN](/article/winnt-vpn.html) creates an encryption overhead (encryption, padding, checksum, etc.), which adds about 100 bytes to the TCPIP-payload. This overhead must not exceed the MTU of the connection as the packets will become fragmented. When the other side receives an encrypted packet it inspects the checksum and it will fail if the packet has been tampered with (fragmented).  
  
 More info [MS KB140375](http://support.microsoft.com/kb/140375 "Default MTU Size for Different Network Topology [Q140375]")  
 More info [MS KB159211](http://support.microsoft.com/kb/159211 "Diagnoses and Treatment of Black Hole Routers [Q159211]")  
 More info [MS KB314496](http://support.microsoft.com/kb/314496 "Default MTU Size for Different Network Topology [Q314496]")  
  
 Related [Recommended settings for the TCP/IP stack](/article/windows-tcpip-settings.html)