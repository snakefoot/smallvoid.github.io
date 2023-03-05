---
title: 'TCP/IP RWIN Auto-Tuning can slow down network'
date: '2007-04-24T01:12:32+02:00'
status: publish
permalink: /article/vista-tcpip-auto-rwin.html
author: Snakefoot
excerpt: 'Not all network routers supports the tcpip receive window scaling flag used by Windows Vista.'
type: post
id: 436
category:
    - Network
    - Network
tag:
    - lan
    - netsh
    - network-performance
    - rwin
    - tcpip
    - wan
post_format: []
tags:
    - 'rwin,lan,wan,tcpip,network-performance,netsh'
---
The network protocol stack has been rewritten in Windows Vista, so it will be even better at adapting to high performance network connections. It is no longer possible to specify a custom size for the [TCP/IP Receive Window (RWIN)](/article/tcpip-rwin-size.html) with the new auto tuning feature (Unless the application it self uses **SO\_RCVBUF**).  
  
 Vista enables Receive Window Scaling by default and when performing the handshake, then it uses a RWIN of 256 bytes with a scale factor of 8 (256^2\*8=64K bytes). This allows the RWIN to reach the size of 16,776,960 bytes.  
  
 Sadly enough not all remote hosts understands the scale factor, and some broken routers might even rewrite the scale factor to zero as packets passes through. Instead of negotiating a RWIN of 65536 bytes then it is only uses 256 bytes. This causes a very slow start or that the connection is dropped completely.  
  
 It possible to change the way it automatically tune the RWIN, so it will use a RWIN of 16,384 bytes with a scale factor of 2 (16384^2\*2=64K bytes). This allows the RWIN to reach the size of 262,140 bytes.

> netsh interface tcp set global autotuninglevel=highlyrestricted

 Note one can disable the autotunning completely, and lock the RWIN to 65536 bytes:
 > netsh interface tcp set global autotuninglevel=disabled

 More Info [MS KB929868](http://support.microsoft.com/kb/929868 "A Web site sends data very slowly or drops the data completely when you use Windows Vista Enterprise")  
 More Info [MS KB932170](http://support.microsoft.com/kb/932170 "When you copy large files to or from earlier operating systems, the copy operation may be slower than expected on some Windows Vista-based computers")  
 More Info [MS KB935400](http://support.microsoft.com/kb/935400 "It takes a very long time to download an e-mail message from a POP3 server in Outlook 2007")  
 More Info [MSDN - WSAIoctl function controls the mode of a socket](http://msdn2.microsoft.com/en-us/library/ms741621.aspx)  
 More Info [The Cable Guy - TCP Receive Window Auto-Tuning](http://www.microsoft.com/technet/technetmag/issues/2007/01/CableGuy/default.aspx)  
 More Info [The Cable Guy - Next Generation TCP/IP Stack](http://www.microsoft.com/technet/community/columns/cableguy/cg1105.mspx "November 2005 - Performance Enhancements in the Next Generation TCP/IP Stack")  
  
 Related [Enable auto-tuning of RWIN in Internet Explorer](/article/ie-http-rwin-tuning.html)  
  
 Credits [www.petri.co.il](http://www.petri.co.il/)