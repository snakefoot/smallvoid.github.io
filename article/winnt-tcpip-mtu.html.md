---
title: 'Configure Max Transfer Unit (MTU) size for the TCPIP stack'
date: '2000-12-31T22:59:22+01:00'
status: publish
permalink: /article/winnt-tcpip-mtu.html
author: Snakefoot
excerpt: 'Changing the Max Transfer Unit (MTU) to avoid packet fragmentation and loss of VPN connection.'
type: post
id: 418
category:
    - Network
    - Network
    - Network
tag:
    - max-transfer-unit
    - tcpip
post_format: []
tags:
    - 'tcpip,max-transfer-unit'
---
The default [Max Transfer Unit (MTU) size](/article/tcpip-mtu-size.html) for ethernet is 1500 bytes, if using a network with a different MTU size, then one should make sure to configure MTU in Windows to avoid packet fragmentation and loss of VPN connections.

- Adapter MTU:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{Adapter-id/GUID}\]  
  >  MTU = 1500  
  >   
  >  More Info [MS KB900926](http://support.microsoft.com/kb/900926 "Recommended TCP/IP settings for WAN links with a MTU size of less than 576 [Q900926]")
- Point-To-Point Protocol (PPP) MTU for Modem DialUp Networking(DUN) or over Ethernet (PPPoE):
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NdisWan \\Parameters \\Protocols \\0\]  
  >  ProtocolType = 0x00000800  
  >  PPPProtocolType = 0x00000021  
  >  ProtocolMTU = 1500  
  >   
  >  More Info [MS KB283165](http://support.microsoft.com/kb/283165 "HOW TO: Change the PPPoE MTU Size in Windows XP [Q283165]")  
  >  More Info [MS KB826159](http://support.microsoft.com/kb/826159 "HOW TO: Change the Default Maximum Transmission Unit (MTU) Size Settings for PPP Connections or for VPN Connections [Q826159]")
  
   More Info [MS KB283070](http://support.microsoft.com/kb/283070 "HOW TO: Create a PPPoE Connection in Windows XP [Q283070]")  
   More Info [MS KB317496](http://support.microsoft.com/kb/317496 "HOW TO: Create a PPPoE Connection in Windows Server 2003 [Q317496]")
- Virtual Private Network (VPN) Tunnel MTU:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NdisWan \\Parameters \\Protocols \\0\]  
  >  ProtocolType = 0x00000800  
  >  PPPProtocolType = 0x00000021  
  >  TunnelMTU = 1400  
  >   
  >  More Info [MS KB826159](http://support.microsoft.com/kb/826159 "HOW TO: Change the Default Maximum Transmission Unit (MTU) Size Settings for PPP Connections or for VPN Connections [Q826159]")
 
 Related [Configure Max Transfer Unit (MTU) in Windows NT4](/article/winnt4-tcpip-mtu.html)  
 Related [Configure Max Transfer Unit (MTU) in Windows Vista/2008/7](/article/vista-tcpip-mtu.html)  