---
title: 'Windows Connect Now - Config Registrar'
date: '2007-07-17T02:17:14+02:00'
status: publish
permalink: /article/winnt-services-wcncsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Connect Now - Config Registrar service.'
type: post
id: 714
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wifi
    - wireless-network
    - wlan
post_format: []
tags:
    - 'wireless-network,wifi,wlan'
---
##### Description:

 WCNCSVC hosts the Windows Connect Now Configuration which is Microsoft's Implementation of Wi-Fi Protected Setup (WPS) protocol. This is used to configure Wireless LAN settings for an Access Point (AP) or a Wi-Fi Device. The service is started programmatically as needed.  
  
 Windows Connect Now (WCN) is a technology which allows one to easily configure a secure wireless network, by using a OOB channel that can be a USB cable or USB flash drive to transfer credentials. A Windows computer acts as registrar and contacts the access point (AP) and performs a handshake where the OOB channel is used to authenticate each other. If a new enrollee (Another Windows Computer) arrives then it will contact the AP, which will forward the notification to the regitrar, and then the OOB mechanism can be used again to authenticate the enrollee. More Info [Microsoft - Windows Connect Now](http://www.microsoft.com/windowsxp/using/networking/getstarted/windowsconnectnow.mspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (wcncsvc)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (wcncsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)