---
title: 'Configure initial congestion window to speed up TCP slow start'
date: '2012-07-19T22:50:13+02:00'
status: publish
permalink: /article/winnt-tcp-slow-start.html
author: Snakefoot
excerpt: 'Description of how TCP slow start can introduce latency for short living and long living TCP connections.'
type: post
id: 834
category:
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
When creating a TCP connection, then it doesn't sent data at full speed, even if the receiving end have setup a large receive-window ([RWIN](/article/tcpip-rwin-size.html)). The sending side will perform a [TCP slow start](http://en.wikipedia.org/wiki/Slow-start), where it first sent 2 frames (MSS) and waits for ACK response, and if no packet drop then it will increase speed exponentially from there. So short living TCP connections, like those to a Web-Server, will experience poor performance (slow latency).  
  
 The TCP slow start will also be activated if there have been no traffic for 200 ms., then the TCP stack will test again if network connection is as good as before. So long living TCP connection, with occasional bursts of data, will experience poor performance (slow latency).  
  
 The initial congestion window size of 2 frames was perfect, when using dialup modems, but with modern network connections, then it is actually a bottleneck. Now the recommended size is 10 frames (MSS).  
  
 It is possible to change the initial congestion window on Windows 2008 R2. This command will display advanced TCP options:

> netsh interface tcp show supplemental  
>   
>  Note the above command will fail if the hotfix [KB2472264](http://support.microsoft.com/kb/2472264 "You cannot customize some TCP configurations by using the netsh command in Windows Server 2008 R2") has not been applied.

 Execution these two commands will set an Initial Congestion Window (ICW) of 10 frames (MSS):
> netsh interface tcp set supplemental template=custom icw=10  
>  netsh interface tcp set supplemental template=custom

 Note for long living TCP connections, then one can workaround the TCP slow start triggered by occasional pause in traffic (Without touching ICW). The simple solution is that the sending side sends a keep alive packet every 150 ms. Alternative the receiving side can cheat and send a ping operation every 150 ms. that causes the sending side to reply back and thus prevent TCP slow start from happening.  
  
 More Info [RFC3390](http://tools.ietf.org/html/rfc3390)  
 More Info [Google 2012: Draft for increasing ICW to 10](http://datatracker.ietf.org/doc/draft-ietf-tcpm-initcwnd/)  
 More Info [Jim Gettys 2012: Increasing ICW to 10 is harmful](http://tools.ietf.org/html/draft-gettys-iw10-considered-harmful-00)  
  
 Related [Compound TCP (CTCP) can improve TCP Slow Start](/article/winnt-ctcp-support.html)  
 Related [TCP\_NODELAY disables nagle algorithm and can improve latency](/article/winnt-nagle-algorithm.html)  
 Related [TCP/IP RWIN Auto-Tuning can slow down network](/article/vista-tcpip-auto-rwin.html)  
  
 Credits [Andy's Notebook](http://www.andysnotebook.com/2011/11/increasing-the-tcp-initial-congestion-window-on-windows-2008-server-r2.html)