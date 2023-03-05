---
title: 'Network Connections'
date: '2000-07-23T15:28:05+02:00'
status: publish
permalink: /article/winnt-services-netman.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network Connections service.'
type: post
id: 565
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Manages objects in the Network and Dial-Up Connections folder, in which you can view both local area network and remote connections.  
  
 Note disabling this service will have certain side effects:
- The Connections folder will not contain any connections, thus preventing dial-out access and configuration of new or existing connections.
- The connection icon in the systray will disappear.
- Network Location-aware Group Policies will not be available through this service.
- Events created from media connects and disconnects will not be made.
- Internet Connection Sharing will not function.

##### Recommended State:

- Manual, if on a simple network or using dialup.

##### Default State:

- Manual

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (Netman)
- WinXP/Win2k3/Win2k: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Netman)

##### Supports:

- [Internet Connection Sharing (ICS)](/article/winnt-services-sharedaccess.html) (Vista+)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html) (Vista+)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)