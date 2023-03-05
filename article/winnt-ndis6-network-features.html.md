---
title: 'NDIS 6 hardware features that increases network performance'
date: '2007-10-31T00:44:39+01:00'
status: publish
permalink: /article/winnt-ndis6-network-features.html
author: Snakefoot
excerpt: 'Windows can activate NDIS 6 network hardware features for offloading the system processor.'
type: post
id: 757
category:
    - Network
    - Network
    - Network
tag:
    - netsh
    - network-interface-card
    - network-performance
    - tcpip
    - tcpip-offload
post_format: []
tags:
    - 'tcpip-offload,network-performance,tcpip,network-interface-card,netsh'
---
Windows 2003 / Vista / 2008 / 7 will detect if the network hardware has capabilities that allows it to offload the CPU.  
  
 Note Windows 2003 SP1 requires the [Scalable Networking Pack](http://support.microsoft.com/kb/912222) to make use of these hardware features (Win2k3 R2 / SP2 has them by default). More Info [MS KB936594](http://support.microsoft.com/kb/936594 "You may experience network-related problems after you install Windows Server 2003 SP2 or the Scalable Networking Pack on a Windows Small Business Server 2003-based computer")  
  
 To see what features currently enabled on the computer:

> netsh int tcp show global

 More Info [Microsoft - Scalable Networking Whitepapers](http://www.microsoft.com/downloads/details.aspx?FamilyID=6aee2e62-b708-44c1-babe-fc0e7b0f02bd "Introduction to the Windows Server 2003 Scalable Networking Pack")  
 More Info [MS Technet - Networking features in Vista / 2008](http://technet.microsoft.com/en-gb/library/bb726965.aspx "New Networking Features in Windows Server 2008 and Windows Vista")  
 More Info [The Cable Guy - Scalable Networking Pack](http://www.microsoft.com/technet/community/columns/cableguy/cg0606.mspx "June 2006 - Microsoft Windows Server 2003 Scalable Networking Pack Overview")  
##### TCP Chimney Offload

 TCP Chimney Offload is an extension of [NDIS 5 offloading](/article/winnt-ndis5-network-features.html) and makes it possible for a Network Interface Card (NIC) to "replace" the Windows TCP stack with its own implementation. When a TCP connection is created in Windows, then the TCP connection state is transfered to the NIC miniport driver (Offload Target), which when completely handles the traffic between the application and the remote host.  
  
 The NIC miniport driver provides a *chimney* that goes from the top to the bottom of the TCP stack, which promises to handle the network traffic (smoke) for the TCP connection. The *chimney* can decide for it self how to keep this promise, and Windows only need to handle the final data transfer to and from the chimney. There are *Vents* in the chimney, so Windows still can access and modify the TCP connection state (ex. if the applications closes or similar events).  
  
 TCP Chimney Offload improves the performance of long-lived connections with large-sized packet payloads, such as those associated with file server, backup and storage workloads and TCP-based multimedia streaming.  
  
 TCP Chimney Offload will automatically be disabled if one of the following features are turned on:
- Windows Firewall (or any other 3rd party firewall)
- Internet Connection Sharing
- Internet Protocol security (IPsec)
- Internet Protocol Network Address Translation (IPNAT)
 
 Note to disable TCP Offload Engine (TOE):
> netsh interface tcp set global chimney=disabled  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnableTCPChimney = 0

 More Info [WHDC - Scalable Networking with TCP Chimney](http://www.microsoft.com/whdc/device/network/tcp_chimney.mspx "Scalable Networking: Network Protocol Offload - Introducing TCP Chimney")  
 More Info [Set chimney state for a particular application.](http://technet.microsoft.com/en-us/library/cc731258(WS.10).aspx "Netsh commands for Interface Transmission Control Protocol")  
 More Info [MS KB951037](http://support.microsoft.com/kb/951037 "Information about the TCP Chimney Offload, Receive Side Scaling, and Network Direct Memory Access features in Windows Server 2008")
 
##### Receive-side Scaling

 Enables use of multiple CPU's to handle the received packets, where the Network Interface Card (NIC) spreads the load to the available CPU's. Instead of using only a single CPU to to process all interrupts from the NIC with the following deferred procedure call (DPC) to process the received data.  
  
 Note the calculations needed to spread the load properly are so CPU intensive, that if they are done in software then it will be slower than not using RSS. The NIC should support the calculation in hardware.  
  
 Note older CPU's like the Intel Pentium 4 and Itanium doesn't support that the DPC is handled by another CPU than the one receiving the interrupt.  
  
 RSS should not be activated if one of the following features are turned on:
- Internet Connection Sharing. More Info [MS KB927695](http://support.microsoft.com/kb/927695 "You cannot host TCP connections when Receive Side Scaling is enabled in Windows Server 2003 with Service Pack 2"), [MS KB927168](http://support.microsoft.com/kb/927168 "TCP traffic stops after you enable both receive-side scaling and Internet Connection Sharing in Windows Vista or in Windows Server 2003 with Service Pack 1")
- ISA Server
 
 Note to disable Receive-side Scaling (RSS):
> netsh interface tcp set global rss=disabled  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnableRSS = 0

 More Info [WHDC - Scalable Networking with RSS](http://www.microsoft.com/whdc/device/network/ndis_rss.mspx)
 
##### Network Direct Memory Access

 NetDMA minimizes the amount of processing that a CPU must do to move packet contents between memory buffers. It requires special hardware like such as Intel I/O Acceleration Technology (Intel I/OAT) available with Intel Xeon processors to function.  
  
 NetDMA will not work together with "TCP Chimney Offload" and requires "Receive-side Scaling". Windows will choose NetDMA if it detects that both NetDMA and TCP Chimney Offload is supported.  
  
 NetDMA will automatically be disabled if one of the following features are turned on:
- Windows Firewall (or any other 3rd party firewall)
- Internet Connection Sharing
- Internet Protocol security (IPsec)
- Internet Protocol Network Address Translation (IPNAT)
 
 Note to disable NetDMA:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnableTCPA = 0  
>   
>  More Info [MS KB947773](http://support.microsoft.com/kb/947773 "A Windows Server 2003-based computer responds slowly to RDP connections or to SMB connections that are made from a Windows Vista-based computer")  
>  More Info [MS KB951037](http://support.microsoft.com/kb/951037 "Information about the TCP Chimney Offload, Receive Side Scaling, and Network Direct Memory Access features in Windows Server 2008")

##### Direct Cache Access

 NetDMA 2.0 (Windows 2008/7) adds support for Direct Cache Access (DCA), that allows the network data to move directly into the CPU cache, instead of the CPU have to spend cycles on retrieving it from the RAM.  
  
 Note to disable NetDCA:
> netsh int tcp set global dca=disable  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnableDCA = 0