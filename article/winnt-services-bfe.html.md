---
title: 'Base Filtering Engine'
date: '2007-07-17T02:12:03+02:00'
status: publish
permalink: /article/winnt-services-bfe.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Base Filtering Engine (BFE) service.'
type: post
id: 660
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - firewall
    - ipsec
post_format: []
tags:
    - 'firewall,ipsec'
---
##### Description:

 The Base Filtering Engine (BFE) is a service that manages firewall and [Internet Protocol security](/article/winnt-services-policyagent.html) (IPsec) policies and implements user mode filtering. Stopping or disabling the BFE service will significantly reduce the security of the system. It will also result in unpredictable behavior in IPsec management and firewall applications.  
  
 More Info [WHDC - Windows Filtering Platform](http://www.microsoft.com/whdc/device/network/WFP.mspx)
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (BFE)

##### Supports:

- [IKE and AuthIP IPsec Keying Modules](/article/winnt-services-ikeext.html)
- [Internet Connection Sharing (ICS)](/article/winnt-services-sharedaccess.html)
- [IPsec Policy Agent](/article/winnt-services-policyagent.html)
- [Network Connectivity Assistant](/article/winnt-services-ncasvc.html) (Win8)
- [Routing and Remote Access](/article/winnt-services-remoteaccess.html)
- [Windows Firewall](/article/winnt-services-mpssvc.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)