---
title: 'Configure Max Transfer Unit (MTU) size for the TCPIP stack'
date: '2000-12-31T22:59:22+01:00'
permalink: /article/winnt-tcpip-mtu.html
author: Snakefoot
excerpt: 'Changing the Max Transfer Unit (MTU) to avoid packet fragmentation and loss of VPN connection.'
type: post
id: 418
categories:
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - max-transfer-unit
    - tcpip
---
The default [Max Transfer Unit (MTU) size](/article/tcpip-mtu-size.html) for ethernet is 1500 bytes, if using a network with a different MTU size, then one should make sure to configure MTU in Windows to avoid packet fragmentation and loss of VPN connections.

- Adapter MTU:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{Adapter-id/GUID}\]  
  >  MTU = 1500  
  >   
  >  More Info <a href="https://www.bing.com/search?q=KB%20900926%20Q900926" rel="nofollow" title="Recommended TCP/IP settings for WAN links with a MTU size of less than 576 [Q900926]">MS KB900926</a>
- Point-To-Point Protocol (PPP) MTU for Modem DialUp Networking(DUN) or over Ethernet (PPPoE):
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NdisWan \\Parameters \\Protocols \\0\]  
  >  ProtocolType = 0x00000800  
  >  PPPProtocolType = 0x00000021  
  >  ProtocolMTU = 1500  
  >   
  >  More Info <a href="https://www.bing.com/search?q=KB%20283165%20Q283165" rel="nofollow" title="HOW TO: Change the PPPoE MTU Size in Windows XP [Q283165]">MS KB283165</a>  
  >  More Info <a href="https://www.bing.com/search?q=KB%20826159%20Q826159" rel="nofollow" title="HOW TO: Change the Default Maximum Transmission Unit (MTU) Size Settings for PPP Connections or for VPN Connections [Q826159]">MS KB826159</a>
  
   More Info <a href="https://www.bing.com/search?q=KB%20283070%20Q283070" rel="nofollow" title="HOW TO: Create a PPPoE Connection in Windows XP [Q283070]">MS KB283070</a>  
   More Info <a href="https://www.bing.com/search?q=KB%20317496%20Q317496" rel="nofollow" title="HOW TO: Create a PPPoE Connection in Windows Server 2003 [Q317496]">MS KB317496</a>
- Virtual Private Network (VPN) Tunnel MTU:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NdisWan \\Parameters \\Protocols \\0\]  
  >  ProtocolType = 0x00000800  
  >  PPPProtocolType = 0x00000021  
  >  TunnelMTU = 1400  
  >   
  >  More Info <a href="https://www.bing.com/search?q=KB%20826159%20Q826159" rel="nofollow" title="HOW TO: Change the Default Maximum Transmission Unit (MTU) Size Settings for PPP Connections or for VPN Connections [Q826159]">MS KB826159</a>
 
 Related [Configure Max Transfer Unit (MTU) in Windows NT4](/article/winnt4-tcpip-mtu.html)  
 Related [Configure Max Transfer Unit (MTU) in Windows Vista/2008/7](/article/vista-tcpip-mtu.html)  