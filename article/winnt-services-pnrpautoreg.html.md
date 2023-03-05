---
title: 'PNRP Machine Name Publication Service'
date: '2007-07-17T02:15:31+02:00'
status: publish
permalink: /article/winnt-services-pnrpautoreg.html
author: Snakefoot
excerpt: 'Description and recommended settings for the PNRP Machine Name Publication Service.'
type: post
id: 693
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - netPeerTcpBinding
    - PNRP
post_format: []
tags:
    - 'PNRP,netPeerTcpBinding'
---
##### Description:

 This service publishes a machine name using the Peer Name Resolution Protocol (PNRP).  
  
 Configuration is managed via the netsh context 'p2p pnrp peer'.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServicePeerNet](/article/winnt-services-wrapper.html) (PNRPAutoReg)
- Vista - [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (PNRPAutoReg)

##### Supports:

- none

##### Depends:

- [Peer Name Resolution Protocol](/article/winnt-services-pnrpsvc.html)