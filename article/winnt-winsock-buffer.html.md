---
title: 'Configure the winsock default send- and receive-buffer size'
date: '2002-10-12T20:18:47+02:00'
status: publish
permalink: /article/winnt-winsock-buffer.html
author: Snakefoot
excerpt: 'Most Windows applications uses Winsock to perform TCPIP communication, and many of these applications uses the default send- and receive-buffer size, which by default isn''t adapted to the available network connection.'
type: post
id: 326
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - network-performance
    - rwin
    - send-window
    - tcpip
    - winsock
post_format: []
tags:
    - 'winsock,send-window,rwin,network-performance,tcpip'
---
Usually when reading about TCPIP there is only mentioned one [Receive Window](/article/tcpip-rwin-size.html) for a connection, which is used to control congestion created by network latency.  
  
 In the WinNT network architecture a layer is placed on top of the TCPIP layer called AFD(Ancillary Function Driver for Winsock). The AFD provides the winsock interface, which is used by most network applications in Windows and is also supporting things like DNS and DHCP.  
  
 The AFD uses two windows which acts as a flowcontrol for the application creating the socket:

- **Send Window**: Used when the application is sending data over a connection, if more data is sent than the receiver is able to acknowledge then the AFD-Send-Window will block the transfer for the application, when it reaches the limit of the AFD-Send-Window. The application creating the socket can use setsockopt to adjust **SO\_SNDBUF**.
- **Receive Window**: Acts just like the TCPIP-Receive Window, and when creating a Winsocket over TCPIP, then AFD will use the TCPIP Receive Window as AFD-Receive Window. The application creating the socket can use setsockopt to adjust **SO\_RCVBUF**.
 
 The default size of the two AFD-Windows is configured at boot time and is dependent on the available amount of physical memory: - 4096 bytes if less than 19 MByte RAM
- 8192 bytes if more than 19 MByte RAM
 
 If using a high latency or high bandwidth network then the AFD windows can affect performance. A small AFD-Send-Window will constantly be blocking the application sending data. A small AFD-Receive-Window will constantly be saturating the application receiving data (And blocking the remote sender). The two AFD-Windows should have the same value as the [optimal TCPIP-Receive-Window](/article/tcpip-rwin-size.html) to get the best speed.  
  
 To set the default size of the AFD-Windows use the following DWORD registry keys:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Afd \\Parameters\]  
>  DefaultReceiveWindow = 16384  
>  DefaultSendWindow = 16384

 Note that the AFD-Windows should be rounded to a multiple of [memory page size](/article/windows-page-file.html) (Usually 4096 Bytes). Not a multiple of the Maximum Segment Size(MSS) which is recommended for the TCPIP-Window.  
  
 Related : [Recommended settings for the TCP/IP stack](/article/windows-tcpip-settings.html)  
  
 More Info [MSDN - Write Scalable Winsock Apps Using Completion Ports](http://msdn.microsoft.com/msdnmag/issues/1000/Winsock/default.aspx)  
 More info [MS KB214397](http://support.microsoft.com/kb/214397 "INFO: Design Issues - Sending Small Data Segments Over TCP w/Winsock [Q214397]")  
 More info [MS KB246984](http://support.microsoft.com/kb/246984 "RPC Programs That Use Winsock Over TCP/IP May Benefit from Tuning [Q246984]")  
 More info [MS KB311084](http://support.microsoft.com/kb/311084 "WinSock Traffic Is Slow Over High Speed, High Latency Links [Q311084]")  