---
title: 'Configure TCPIP Max Transfer Unit (MTU) size'
date: '2007-07-05T02:43:11+02:00'
status: publish
permalink: /article/vista-tcpip-mtu.html
author: Snakefoot
excerpt: 'Changing the Max Transfer Unit (MTU) to avoid packet fragmentation and connection loss.'
type: post
id: 656
category:
    - Network
    - Network
tag:
    - max-transfer-unit
    - netsh
    - tcpip
post_format: []
tags:
    - 'max-transfer-unit,tcpip,netsh'
---
The default [Max Transfer Unit (MTU) size](/article/tcpip-mtu-size.html) for ethernet is 1500 bytes, if using a network with a different MTU size, then one should make sure to configure MTU in Windows to avoid packet fragmentation or connection loss.  
  
 Open an [Elevated Command Prompt](/article/winnt-user-account-protection.html#ELEVATED) and run this command to view current MTU size of the available IPv4 sub-interfaces (Can also be done with IPv6):

> netsh interface ipv4 show interfaces

 To change the MTU size of sub-interface no. 1 (See "Idx" from above command):
 > netsh interface ipv4 set subinterface interface=1 mtu=1500 store=persistent

 Related [Registry settings to Configure MTU size](/article/winnt-tcpip-mtu.html).  