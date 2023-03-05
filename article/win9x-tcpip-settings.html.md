---
title: 'Configure TCPIP stack settings in Windows 9x'
date: '2001-01-01T15:35:24+01:00'
status: publish
permalink: /article/win9x-tcpip-settings.html
author: Snakefoot
excerpt: 'Description of the registry keys used for configuring the TCP/IP stack in Windows 95 / 98 / Me.'
type: post
id: 190
category:
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
    - 'tcpip,lan,wan,rwin,max-transfer-unit,network-performance'
---
It is recommended to read [how to configure TCPIP for optimal performance](/article/windows-tcpip-settings.html) before changing any of the registry settings specified here, as there exists utilities that are much easier to use than the registry editor when configuring the TCPIP stack.  
  
 Note for Win95 users who haven't updated to Winsock2, should use the datatype DWORD, and not STRING as shown here.  
 Windows 98 and Windows Me comes with Winsock2 installed by default and should use the datatype STRING, except for settings below the "Parameters"-key.  
  
**Receive WINdow** (RWIN) is configured in bytes:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
>  DefaultRcvWindow = "17520" (Standard Range "0-65535", Window Scaling Range "0-1GByte", Default - calculated)  
>   
>  Related [Finding the optimal TCPIP receive window size](/article/tcpip-rwin-size.html)

 **Maximum Receive WINdow** is configured in bytes. To ensure that Window Scaling doesn't create receive windows that takes too much memory (Win98/WinME Only):
 
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP \\Parameters\]  
 >  GlobalMaxTcpWindowSize = 17520 (DWORD Standard Range 0-65535, Window Scaling Range 0-1GByte, Default not set)  
 >   
 >  GlobalMaxTcpWindoSize = 17520 (Win98 Spelling Error, Best to set both, More info [MS KB239731](http://support.microsoft.com/kb/239731 "Unable to Set the TCP/IP GlobalMaxTcpWindowSize Parameter in Windows 98 [Q239731]"))

 **Time To Live** (TTL):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  DefaultTTL = "64" (Range = "0-255", Default = "32")

 **Path MTU Black Hole Detection**:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  PMTUBlackHoleDetect = "0" (Enabled = "1", Disabled = "0", Default = "0")

 **Path MTU Discovery** (Winsock2 Only):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  PMTUDiscovery = "1" (Enabled = "1", Disabled = "0", Default = "1")

 **Selective Acknowledgements** (ACK's) (Winsock2 Only):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  SackOpts = "1" (Enabled = "1", Disabled = "0", Default = "0")

 **Receive Window Scaling and Time Stamping** (Winsock2 Only):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\]  
 >  Tcp1323Opts = "3" (Both Disabled = "0", Window Scaling Only = "1", Timestamp Only = "2", Both Enabled = "3", Default = No value; only initiate the options if requested.)  
>   
>  More Info [MS KB239705](http://support.microsoft.com/kb/239705 "RFC 1323 Options Can Not Be Enabled in Windows 95 and Windows 98 [Q239705]") Fix [MS KB236926](http://support.microsoft.com/kb/236926 "Windows 95 and Windows 98 TCP/IP May Retransmit Packets Prematurely [Q236926]")

 **Max Duplicate Acknowledgments** (ACK's) (Winsock2 Only):
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\MSTCP\\ Parameters\]  
 >  MaxDupAcks = 2 (DWORD Range = 1-3, Default = 3)

 Note none of the above settings are created by default, so to revert to default values then just remove the settings.  
  
 More Info [MS KB182108](http://support.microsoft.com/kb/182108 "Availability of Windows Sockets 2.0 for Windows 95 [Q182108]")  
 More Info [Windows TCP/IP Registry Entries \[Q158474\]](http://support.microsoft.com/kb/158474)  
 More Info [MS TCP/IP and Windows 95 Networking](http://www.microsoft.com/technet/archive/win95/mstcpip.mspx)  
  
 Credits [regedit.com](http://registry.winguides.com/display.php/646/)  