---
title: 'Network Store Interface Service'
date: '2007-07-17T02:14:51+02:00'
status: publish
permalink: /article/winnt-services-nsi.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network Store Interface Service.'
type: post
id: 685
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 This service delivers network notifications (e.g. interface addition/deleting etc) to user mode clients. Stopping this service will cause loss of network connectivity. If this service is disabled, any other services that explicitly depend on this service will fail to start.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (nsi)

##### Supports:

- [DHCP Client](/article/winnt-services-dhcp.html)
- [DNS Client](/article/winnt-services-dnscache.html)
- [IP Helper](/article/winnt-services-iphlpsvc.html)
- [Network Connections](/article/winnt-services-netman.html)
- [Network Location Awareness](/article/winnt-services-nla.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)
- [Network Connectivity Assistant](/article/winnt-services-ncasvc.html) (Win8+)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (Win8+)