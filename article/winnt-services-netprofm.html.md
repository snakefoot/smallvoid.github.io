---
title: 'Network List Service'
date: '2007-07-17T02:14:47+02:00'
status: publish
permalink: /article/winnt-services-netprofm.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network List Service.'
type: post
id: 684
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Identifies the networks to which the computer has connected, collects and stores properties for these networks, and notifies applications when these properties change.  
  
 Note disabling this service will have certain side effects:
- "Network and Sharing Center" will not be able to detect the status of the network.
- The connection icon in the system tray will not be able to display the network connection status.

##### Recommended state:

- Manual

##### Default State:

- Win8/Win7 - Manual
- Vista - Automatic

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (netprofm)

##### Supports:

- [SL UI Notification Service](/article/winnt-services-sluinotify.html) (Vista only)
- [HomeGroup Provider](/article/winnt-services-homegroupprovider.html) (Win7+)
- [Network Connected Devices Auto-Setup](/article/winnt-services-ncdautosetup.html) (Win8+)

##### Depends:

- [Network Location Awareness](/article/winnt-services-nla.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)