---
title: 'Keberos Key Distribution Center'
date: '2000-07-23T13:47:02+02:00'
status: publish
permalink: /article/winnt-services-kdc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Keberos Key Distribution Center service.'
type: post
id: 557
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 It provides two services (TCPIP Port 88): - **Authentication Service**: Issues Ticket-Granting Tickets (TGTs) to allow connection to the "Ticket-Granting Service" in a trusted domain.
- **Ticket-Granting Service (TGS)**: Issues tickets for making connections to computers in the local domain for clients having a TGT.
 
 More Info [MS KB235529](http://support.microsoft.com/kb/235529 "Kerberos Support on Windows 2000-Based Server Clusters [Q235529]")  
 More Info [MS KB262177](http://support.microsoft.com/kb/262177 "HOW TO: Enable Kerberos Event Logging [Q262177]")  
  
##### Recommended State:

- Disabled, if on a simple home network.

##### Default State:

- Disabled.

##### Process Name:

- [lsass.exe](/article/winnt-services-wrapper.html) (Kdc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)