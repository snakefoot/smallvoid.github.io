---
title: 'Peer Networking Identity Manager'
date: '2007-07-17T02:15:17+02:00'
status: publish
permalink: /article/winnt-services-p2pimsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Peer Networking Identity Manager service.'
type: post
id: 690
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

 Provides identity services for the Peer Name Resolution Protocol (PNRP) and Peer-to-Peer Grouping services. If disabled, the Peer Name Resolution Protocol (PNRP) and Peer-to-Peer Grouping services may not function, and some applications, such as HomeGroup (Win8/Win7) and Remote Assistance, may not function correctly.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServicePeerNet](/article/winnt-services-wrapper.html) (p2pimsvc)
- Vista - [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (p2pimsvc)

##### Supports:

- none

##### Depends:

- [Peer Name Resolution Protocol](/article/winnt-services-pnrpsvc.html)
- [Peer Networking Grouping](/article/winnt-services-p2psvc.html)