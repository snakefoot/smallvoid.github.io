---
title: 'Peer Networking Grouping'
date: '2007-07-17T02:15:12+02:00'
status: publish
permalink: /article/winnt-services-p2psvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Peer Networking Grouping service.'
type: post
id: 689
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

 Enables multi-party communication using Peer-to-Peer Grouping. If disabled, some applications, such as HomeGroup (Win7), may not function.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServicePeerNet](/article/winnt-services-wrapper.html) (p2psvc)
- Vista - [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (p2psvc)

##### Supports:

- none

##### Depends:

- [Peer Name Resolution Protocol](/article/winnt-services-pnrpsvc.html)
- [Peer Networking Identity Manager](/article/winnt-services-p2pimsvc.html)