---
title: 'Activate support for Explicit Congestion Notification (ECN)'
date: '2008-12-23T04:29:12+01:00'
status: publish
permalink: /article/winnt-ecn-support.html
author: Snakefoot
excerpt: 'Explicit Congestion Notification improves congestion handling for the TCP/IP protocol.'
type: post
id: 783
category:
    - Network
    - Network
tag:
    - netsh
    - network-congestion
    - network-performance
    - tcpip
post_format: []
tags:
    - 'network-congestion,tcpip,network-performance,netsh'
---
When a network router becomes overloaded, then it usually signals this by dropping packets. The receiver then suddenly has to ask for retransmission of packets, and then the sender knows something is wrong and will perform a slow start.  
  
 The slow start causes the connection speed to be halved, and then slowly increase speed from there. This is bad for high bandwidth connection, which f.ex. is used for streaming media. Instead of the network router pulling the handbrake, then it would be nice if it could signal the receiver and sender, that they should lower the speed a little.  
  
 Explicit Congestion Notification (ECN) specifies that the network router can set a reserved bit in the TCP/IP-header ([RFC 3168](http://www.faqs.org/rfcs/rfc3168.html)). When the receiver get packets with the ECN bit set, then it will know that the network router is having trouble, and will send a packet to the sender telling that it should slow down a little.  
  
 ECN only works if all parties (sender, receiver, network router) recognizes the ECN bits. There are even some routers that will drop packets if they detect that ECN bits are used. Windows Vista/2008 supports ECN, but it is disabled by default. To activate ECN support:

> netsh interface tcp set global ecncapability=enabled

 More Info [Cable Guy - ECN](http://technet.microsoft.com/en-us/library/bb878122.aspx "The Cable Guy - October 2006 - Explicit Congestion Notification (ECN) for TCP/IP")  
 More Info [Wiki - ECN](http://en.wikipedia.org/wiki/Explicit_Congestion_Notification)