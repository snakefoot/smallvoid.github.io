---
title: 'Disable IPv6 imaginary tunnel network interfaces'
date: '2016-08-29T22:23:37+02:00'
status: publish
permalink: /article/winnt-ipv6-network-tunnel.html
author: Snakefoot
excerpt: 'IPv6 network tunnel interfaces makes you open for network attacks, and introduces an overhead.'
type: post
id: 5351
category:
    - Network
    - Network
tag:
    - 6to4
    - ipv4
    - ipv6
    - isatap
    - tcpip
    - teredo
post_format: []
---
Windows is now ready for IPv6, but lots of places still uses IPv4. Microsoft have implemented different network tunnel interfaces, that allows IPv6-islands to communicate over the IPv4-sea.

- **6to4** - Very simple network tunnel, that doesn't support NAT-routers. More Info [Wiki](https://en.wikipedia.org/wiki/6to4)
- **Teredo** - Uses external Microsoft Teredo servers to enable tunnel in network with NAT-routers. More Info [Teredo](https://en.wikipedia.org/wiki/Teredo_tunneling)
- **ISATAP** - Allows an internal network to use IPv6 and IPv4 side-by-side until all devices are ready to use IPv6. More Info [ISATAP](https://en.wikipedia.org/wiki/ISATAP)
 
 Most home users just uses the network-router received from their ISP, which either gets an external IPv4- or IPv6-address. The ISP network-router will then create an internal IPv4-network, so all the home-devices will just use IPv4.  
  
 These network tunnel implementations can open up to network attacks from the outside, where outsiders performs spoofing to simulate them being part of the internal network. The network tunnel implementations also introduces an overhead, as the constant translation is always in effect. More Info [MS16-077](https://technet.microsoft.com/en-us/library/security/ms16-077.aspx)  
  
 Home users that are not in transition to upgrade to pure IPv6, should consider to disable these virtual network interfaces:
>  netsh interface ipv6 6to4 set state state=disabled undoonstop=disabled  
>  netsh interface teredo set state disabled  
>  netsh interface ipv6 isatap set state state=disabled

 Credits [Mark Minasi](http://www.minasi.com/newsletters/nws1303.htm)