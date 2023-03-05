---
title: 'Faster boot times by using static IP instead of DHCP'
date: '2001-01-01T02:55:11+01:00'
status: publish
permalink: /article/dhcp-static-ip.html
author: Snakefoot
excerpt: 'Description of how to configure a computer network without a DHCP server.'
type: post
id: 140
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - boot-time
    - default-gateway
    - dhcp
    - network-router
    - tcpip
post_format: []
tags:
    - 'tcpip,dhcp,network-router,default-gateway,boot-time'
---
Windows configures by default all network adapters to use the network protocol TCP/IP and to use a DHCP server to assign an IP address. The TCP/IP protocol requires that each computer in the computer network has an unique IP address, and the DHCP server is able to make sure this happens.  
  
 If there is no DHCP server present in the network, then the computers will stall at bootup while waiting for a response from the non-existing DHCP server. If there is no DHCP server on the network, then it can be a good idea to use a static IP and stop the waiting for a DHCP server and the performing of [Automatic TCP/IP Addressing](/article/automatic-tcpip-addressing.html).  
  
 To see what IP address the computer is using run this from a command prompt:

> ipconfig /all

 If the assigned IP address is 0.0.0.0 or 169.254.x.x, then it means that it tried to use the DHCP server but failed. If this is the case then one should consider using a static IP instead instead of waiting for the DHCP server.  
  
 To create a network where all computers connected are using static IP addresses, then use the following setup:
> IP Address : 192.168.1.x  
>  Subnet Address : 255.255.255.0  
>  Default Gateway : 192.168.1.1

 The IP Address "x" is a number between 1 and 255 and each computer in the network must be assigned their own unique number. If a router is used to connect to the Internet, then it should be assigned the IP address of the default gateway, and all computers should have their default gateway set to that IP address (Along with setting the Primary DNS IP to point to the Internet Service Provider (ISP) DNS server).