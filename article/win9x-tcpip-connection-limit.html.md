---
title: 'Increase the limit of concurrent TCPIP connections in Windows 9x'
date: '2001-01-01T16:04:45+01:00'
status: publish
permalink: /article/win9x-tcpip-connection-limit.html
author: Snakefoot
excerpt: 'Configuring the TCPIP stack to increase the amount of concurrent connections in Windows 95 / 98 / Me.'
type: post
id: 192
category:
    - Network
    - Network
    - Network
tag:
    - network-performance
    - tcpip
post_format: []
tags:
    - 'tcpip,network-performance'
---
There is built in a limit for how many simultaneous connections can be made by Windows. This limit can constraining when running a server like MySQL, FTP, HTTP, FileSharing etc. This limit can be changed in the registry with this STRING value:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
>  MaxConnections = "255" (Default = "100")  
>   
>  Note if using Win95 without having Winsock2 installed the datatype should be a DWORD.  
>   
>  Note that there is rumors that it cannot handle a limit beyond 300 connections, and some cannot even rise the value above 100.  
>   
>  More Info [MS KB243116](http://support.microsoft.com/kb/243116 "Only a Certain Number of Clients Can Join a NetMeeting Conference [Q243116]")

 Note if using an application that frequently opens and closes connections, then it might run out connections because after closing a connection, the connection is locked to make sure the other party has acknowledged that the connection is closed. To shorten the time (in seconds) the connection is locked:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  TcpTimedWaitDelay = "120" (Default = 240 secs)

 Note if using an application that doesn't have a builtin keep alive mechanism, and relies on the TCPIP timeout checking (Every 2 hours). Then one might end up with connections that "never" closes. To shorten the interval between each TCPIP timeout check:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  KeepAliveTime = "1800000" (Default = 7,200,000 milisecs)

 Related [Configure TCPIP stack settings in Windows 9x](/article/win9x-tcpip-settings.html)