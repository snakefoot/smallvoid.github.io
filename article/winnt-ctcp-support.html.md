---
title: 'Compound TCP (CTCP) can speed up TCP Slow Start'
date: '2009-08-14T01:12:21+02:00'
status: publish
permalink: /article/winnt-ctcp-support.html
author: Snakefoot
excerpt: 'Compound TCP (CTCP) can improve the throughput for high bandwidth and high latency connections, by improving TCP slow start.'
type: post
id: 789
category:
    - Network
    - Network
    - Network
tag:
    - netsh
    - network-congestion
    - network-performance
    - rwin
    - tcpip
post_format: []
tags:
    - 'rwin,network-congestion,tcpip,network-performance,netsh'
---
Microsoft have implemented their own homemade congestion provider as an alternative to the standard TCP congestion provider. It is called Compound TCP (CTCP) and attempts to help certain connection types where TCP Slow Start takes forever:

- High bandwidth connections requiring very large receive windows (RWIN)
- Lossy connections requires lots of retransmission if the RWIN is too large.
 
 These types of connection are becoming more common, as more international companies want to connect their different long distance offices with high speed connections.  
  
[TCP slow start](http://en.wikipedia.org/wiki/Slow-start) is a way to probe the network connection, where one "slowly" increases the TCP Send Window as one verifies that the network connection can handle it. If retransmissions are required then it will slow down the growth of the TCP Send Window. If having a high bandwidth and high latency connection, then it might take an hour or more for TCP to make use of the full bandwidth. CTCP allows the TCP Send Window to grow faster, even if retransmissions are needed, but only if it detects that network connection can handle it.  
  
 To change the congestion provider to CTCP (default on Windows 2008):
 > netsh interface tcp set global congestionprovider=ctcp

 To revert the congestion provider to default TCP (default on Windows Vista):
 > netsh interface tcp set global congestionprovider=none

 More Info [Wiki - Compound TCP](http://en.wikipedia.org/wiki/Compound_TCP)  
 More Info [Microsoft Research - Document about CTCP](http://research.microsoft.com/apps/pubs/default.aspx?id=70189 "A Compound TCP Approach for High-speed and Long Distance Networks")  
 More Info [Cable Guy - Compound TCP](http://technet.microsoft.com/en-us/library/bb878127.aspx "The Cable Guy - November 2005 - Performance Enhancements in the Next Generation TCP/IP Stack")  
 More Info [MS KB949316](http://support.microsoft.com/kb/949316 "Description of a hotfix that adds Compound TCP (CTCP) support to computers that are running Windows Server 2003 or a 64-bit version of Windows XP") (Hotfix for Win2k3 enables CTCP)  
  
 Related [Configure initial congestion window to speed up TCP slow start](/article/winnt-tcp-slow-start.html)  
 Related [TCP/IP RWIN Auto-Tuning](/article/vista-tcpip-auto-rwin.html)  