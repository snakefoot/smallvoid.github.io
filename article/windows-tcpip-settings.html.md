---
title: 'Configure TCPIP settings for better performance'
date: '2002-06-19T11:56:28+02:00'
status: publish
permalink: /article/windows-tcpip-settings.html
author: Snakefoot
excerpt: 'Increase the speed of the network connection by changing the TCP/IP settings.'
type: post
id: 187
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
    - rwin
    - tcpip
    - wan
post_format: []
tags:
    - 'tcpip,rwin,max-transfer-unit,lan,wan,network-performance'
---
Description of what TCP/IP settings to configure for better performance and quality connection. These settings are configured through the Windows registry, but there also exist utilities to easily configure these settings:

- [DSLReport's DrTCP](http://www.dslreports.com/drtcp) - Utility to configure the most common settings (Recommended).
- [SpeedGuide's TCP Optimizer](http://www.speedguide.net/downloads.php) - Utility to configure almost everything and includes a connection speed tester to give recommendations
- If wanting to get your hands dirty, then here are details of where to go in the registry: 
  - Registry settings for the TCP/IP stack [Win9x](/article/win9x-tcpip-settings.html) / [WinNT](/article/winnt-tcpip-settings.html)
  - Registry settings for the MTU size [Win9x](/article/win9x-tcpip-mtu.html) / [WinNT](/article/winnt-tcpip-mtu.html)
 
 Note that most settings will affect all network connections, so if connected to a home LAN and also the Internet WAN, then the communication to both networks will be changed when changing the TCPIP settings.
- **Receive Window** (DefaultRcvWindow/TcpWindowSize) specifies how much data it will accept without an acknowledgment. See how to [find the optimal TCPIP RWIN (Receive WINdow) size](/article/tcpip-rwin-size.html).  
   Note to be able to use a Receive Window larger than 65535 bytes, one have to enable Receive Window Scaling according to [RFC 1323](http://www.faqs.org/rfcs/rfc1323.html).
- **Max Transfer Unit (MTU)** specifies how large packets of data it will accept to send and receive. See how to [find the optimal Max Transfer Unit (MTU) size](/article/tcpip-mtu-size.html).  
   Note the MTU is usually set for the individual network adapter, so it will only affect networks which the adapter connects to.  
   Note also that if the adapter is used for several networks like LAN and Internet then optimizing for one network might degrade the others.
- **Time To Live (TTL)** (DefaultTTL) specifies how many seconds/hobs a TCP/IP packet will live before dying. If it is set too high it will take a long time to timeout, if it is set too low it will not be able to reach destination before dying.  
   The recommended value is 64.
- **Path MTU Black Hole Detection** (PMTUBlackHoleDetect/EnablePMTUBHDetect) specifies if it should be able to detect routers, which doesn't respond back if they get packets larger than their Max Transmission Unit (MTU) size. When enabled it will detect if too many re-transmissions, and will then clear the Don't Fragment (DF)-flag, and if transmission succeeds, then it will lower the [MTU size](/article/tcpip-mtu-size.html) for the connection and enable the DF-flag again.  
   The recommended setting is disabled.
- **Path MTU Discovery** (PMTUDiscovery) enables detection of Max Transmission Unit(MTU). This allows the TCPIP stack to discover the optimal MTU for the connection, making sure packets are not fragmented. MTU discovery can cause some slow down when establishing the connection, according to [RFC 1191](http://www.faqs.org/rfcs/rfc1191.html), but if disabled then it will use a [MTU size](/article/tcpip-mtu-size.html) of 576.  
   The recommended setting is enabled.
- **Selective Acknowledgement (SACK)** operation (SackOpts) allows TCP to recover from IP packet loss without resending packets that were already received by the receiver. This especially helps if having a large receive window. If connecting to a service which does not comply with [RFC 2018](http://www.faqs.org/rfcs/rfc2018.html) then the connection will be slower with this enabled.  
   The recommended setting is enabled.
- **Receive Window Scaling and Time Stamping** (Tcp1323Opts) allows the use of a Receive beyond 65535 bytes and the use of Time Stamping to calculate Round Trip Time(RTT) to better scale the receive window according to [RFC 1323](http://www.faqs.org/rfcs/rfc1323.html). The window scaling and timestamp enables automatic handling of: 
  - Adapting the receive window to the actual connection bandwidth. The sender performs a "slow start" where the announced receive window is increased exponential until packet loss is detected, where it lowers the receive window and then increases it linear until packet loss is again detected. This makes configuration of the [optimal receive window](/article/tcpip-rwin-size.html) less important.  
       This doesn't work well with high bandwidth connections with high latency [RFC 3649](http://www.faqs.org/rfcs/rfc3649.html).
  - Adapting the receive window when congestion is detected due to packet loss. The sender lowers the announced receive window and performs a "slow start".  
       This doesn't work well when needing a certain quality of service for special applications [RFC 3168](http://www.faqs.org/rfcs/rfc3168.html).
   
   The timestamp also helps identifying an individual packet on a high bandwidth network (GBit), where the packet sequence number can be reused faster than the TTL of the packet according to [RFC 1185](http://www.faqs.org/rfcs/rfc1185.html). If timestamps are enabled then the size of the TCP Header will be increased with 12 bytes, and will leave less room for data.  
   The recommended setting is to have both enabled with broadband, else only Window Scaling.
- **Max Duplicate Acknowledgments** (MaxDupAcks) specifies that the sender is able to do a fast retransmit of a lost packet before Retransmission TimeOut (RTO) [RFC 2001](http://www.faqs.org/rfcs/rfc2001.html). When a packet is sent a timer is set and if it reaches RTO the packet will be resend. When a packet-number is received and it is out of order an acknowledgment (ACK) is sent with the expected packet-number. This option allows the sender to retransmit the packet before the RTO, if it gets duplicate ACK with the same packet-number.  
   The recommended value is 2 duplicates.