---
title: 'Secure Socket Tunneling Protocol Service'
date: '2008-02-23T14:30:23+01:00'
status: publish
permalink: /article/winnt-services-sstpsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Secure Socket Tunneling Protocol service.'
type: post
id: 764
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - VPN
post_format: []
tags:
    - VPN
---
##### Description:

 Provides support for the Secure Socket Tunneling Protocol (SSTP) to connect to remote computers using VPN. If this service is disabled, users will not be able to use SSTP to access remote servers.  
  
 SSTP allows traffic to pass through firewalls that block PPTP and L2TP/IPsec traffic. It encapsulates PPP traffic over the SSL channel of the HTTPS protocol (Port 443). It allows clients behind firewalls and NAT routers to connect to the VPN server without the concern for typical port blocking issues.  
  
 More Info [The Cable Guy - SSTP](http://www.microsoft.com/technet/technetmag/issues/2007/06/CableGuy/ "The Secure Socket Tunneling Protocol")  
 More Info [MS KB947032](http://support.microsoft.com/kb/947032 "How to configure a Secure Socket Tunneling Protocol (SSTP)-based VPN server behind a NAT device in Windows Server 2008") (How to configure SSTP)  
 More Info [MS KB947031](http://support.microsoft.com/kb/947031 "How to troubleshoot Secure Socket Tunneling Protocol (SSTP)-based connection failures in Windows Server 2008") (How to troubleshoot SSTP)  
##### Recommended state:

- Manual.

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (SstpSvc)

##### Supports:

- [Remote Access Connection Manager](/article/winnt-services-rasman.html)

##### Depends:

- None