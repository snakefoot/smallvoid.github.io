---
title: 'Configure Max Transfer Unit (MTU) size for the TCPIP stack'
date: '2000-12-31T22:47:43+01:00'
status: publish
permalink: /article/winnt4-tcpip-mtu.html
author: Snakefoot
excerpt: 'Changing the Max Transfer Unit (MTU) to avoid packet fragmentation and loss of VPN connection.'
type: post
id: 417
category:
    - Network
tag:
    - max-transfer-unit
    - tcpip
post_format: []
tags:
    - 'tcpip,max-transfer-unit'
---
The default [Max Transfer Unit (MTU) size](/article/tcpip-mtu-size.html) for ethernet is 1500 bytes, if using a network with a different MTU size, then one should make sure to configure MTU in Windows to avoid packet fragmentation and loss of VPN connections.  
  
 If having several adapters in the registry, one can find the wanted Adapter, by making changes to the TCPIP configuration for the Adapter in Network Properties. Example set an odd DNS-Address for TCPIP protocol bound to the adapter, and then look at the TCPIP setting for each adapter to find the odd DNS-Address.  
  
 To configure MTU in WinNT4:

- Adapter MTU (Go to the Services-key and do a search for "TCPIP" to find the different adapters using TCPIP)
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\{Adapter-Name} \\Parameters \\Tcpip\]  
  >  MTU = 1500
- Point-To-Point Protocol (PPP) MTU (WinNT4 SP4+)
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet\\Services \\NdisWan \\Parameters\]  
  >  IPMTU = 1500  
  >   
  >  More Info [MS KB183229](http://support.microsoft.com/kb/183229 "RAS Uses Fixed TCP/IP MTU Size [Q183229]")
- Virtual Private Network (VPN) Tunnel MTU (WinNT4 SP4+)
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet\\Services \\NdisWan \\Parameters\]  
  >  TunnelMTU= 1400  
  >   
  >  More Info [MS KB183229](http://support.microsoft.com/kb/183229 "RAS Uses Fixed TCP/IP MTU Size [Q183229]")
 
 Related [Configure Max Transfer Unit (MTU) in Windows 2000 / XP](/article/winnt-tcpip-mtu.html)