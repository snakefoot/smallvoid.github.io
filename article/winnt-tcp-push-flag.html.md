---
title: 'Improve latency for TCP by not waiting for Push flag'
date: '2012-02-28T02:10:41+01:00'
status: publish
permalink: /article/winnt-tcp-push-flag.html
author: Snakefoot
excerpt: 'Description of how the Push Flag in the TCP Header can optimize network buffer usage, but can increase latency.'
type: post
id: 833
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - network-performance
    - tcpip
post_format: []
tags:
    - 'network-performance,tcpip'
---
When communicating using TCP then the TCP layer attempts to optimize performance by bundling data into chunks. This works well when performing file transfers and other large data transfers. One of the flags in the [TCP Header](http://en.wikipedia.org/wiki/Transmission_Control_Protocol) is the Push Flag (PSH bit).  
  
 The Push Flag is used by the sending side to mark that it is end of a data chunk (Ex. end of data header or data body being sent). This tells the TCP layer on the receiving side to flush the received data to the receiving application without waiting for the receive buffer to be filled. The setting of the Push Flag is usually not controlled by the sending application, but by the sending TCP layer. Most modern TCP/IP stacks set the PSH bit at the end of the buffer supplied to send() . The Push Flag helps the receiving side to optimize throughput by bundling data into logical chunks.  
  
 But the receiving application might want to get the data from the TCP layer as soon as it arrives, instead of having the data waiting in the TCP layer for buffer optimization.

- Streaming movies or music, where the application playing the stream needs the data as soon as possible.
- Low latency application like online games, where the application wants to be closely synchronized with the server as possible.
 
 Usually low latency application and streaming application skips the TCP layer, because many of the "optimizations" implemented in the TCP layer usually sacrifices latency to increase data throughput. Instead low latency applications uses the UDP layer directly, and implement their own retransmission protocol if needed.
 
##### Small Receive Buffer to avoid delay

 If in a situation where the TCP layer is forced, and low latency is crucial, then the receiving application should [recv()](http://msdn.microsoft.com/en-us/library/windows/desktop/ms740121.aspx) into a small buffer to improve latency. The receive buffer (provided by the receiving application) should not be confused with the [receive window](/article/tcpip-rwin-size.html) (provided by the receiving TCP layer).  
  
 The recv() / WSARecv() calls returns when one of the following events occurs:
- Data arrives with the PUSH bit set.
- The user recv buffer is full.
- 0.5 seconds have elapsed since any data has arrived.

##### Disable PUSH-bit optimization completely

 It is possible to disable the Push Flag buffer optimization for the TCP layer on the receiving side to avoid the delay. It will affect the performance for all TCP/IP connections, but it can remove the unwanted delay. This can be useful if not able to get the sending application to use PUSH bit (Linux/Telnet), and it is not possible to change recv-buffer for the receiving application.
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Afd \\Parameters\]  
>  IgnorePushBitOnReceives = 1  
>   
>  Note this will affect all TCP connections created by any application on the system.

 More Info [MS KB126967](http://support.microsoft.com/kb/126967 "New TCP/IP Registry Parameter Ignores Push Bit on Receives")  
##### Disable PUSH-bit optimization on single socket

 Windows 8.1 / Windows 2012 have made it possible to disable the PUSH-bit optimization when receiving from a single TCP-connection.  
  
 Add the **MSG\_PUSH\_IMMEDIATE**-flag when calling [WSARecv()](https://msdn.microsoft.com/en-us/library/windows/desktop/ms741688.aspx).
 
##### Large Send Buffer to avoid delay

 The sending application can also fix the issue by ensuring that the TCP Send Operation Buffer is one byte smaller than the TCP Socket Send Buffer. This is done by calling **setsockopt(SO\_SNDBUF)** with a socket-buffer-size of 64 KByte, and calling **WSASend** with a user-buffer-size of 32 KByte. This will ensure that the TCP Push-bit is set for every TCP-send operations, and avoid [delayed ACK](/article/winnt-nagle-algorithm.html) issues as data is broken into chunks. More Info [MS KB823764](http://support.microsoft.com/kb/823764 "Slow performance occurs when you copy data to a TCP server by using a Windows Sockets API program")  
  
 If unable to fix the sending application, then one can also use this registry key:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Afd \\Parameters\]  
>  NonBlockingSendSpecialBuffering = 1  
>   
>  Note this will affect all TCP connections created by any application on the system.

   
 Related [TCP\_NODELAY disables nagle algorithm and can improve latency](/article/winnt-nagle-algorithm.html)