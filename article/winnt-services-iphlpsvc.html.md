---
title: 'IP Helper'
date: '2007-07-17T02:14:14+02:00'
status: publish
permalink: /article/winnt-services-iphlpsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the IP Helper service.'
type: post
id: 676
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - ipv4
    - ipv6
    - tcpip
post_format: []
tags:
    - 'ipv6,ipv4,tcpip'
---
##### Description:

 Provides tunnel connectivity using IPv6 transition technologies (6to4, ISATAP, Port Proxy, and Teredo), and IP-HTTPS. If this service is stopped, the computer will not have the enhanced connectivity benefits that these technologies offer.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (iphlpsvc)

##### Supports:

- [Network Connectivity Assistant](/article/winnt-services-ncasvc.html) (Win8+)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Windows Management Instrumentation](/article/winnt-services-winmgmt.html)