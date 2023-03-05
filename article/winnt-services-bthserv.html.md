---
title: 'Bluetooth Support Service'
date: '2009-09-16T11:13:42+02:00'
status: publish
permalink: /article/winnt-services-bthserv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Bluetooth Support Service.'
type: post
id: 797
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - bluetooth
post_format: []
tags:
    - bluetooth
---
##### Description:

 The Bluetooth service supports discovery and association of remote Bluetooth devices. Stopping or disabling this service may cause already installed Bluetooth devices to fail to operate properly and prevent new devices from being discovered or associated.  
  
 More Info [Bluetooth (Wiki)](http://en.wikipedia.org/wiki/Bluetooth)
 
##### Recommended state:

- Manual

##### Default State:

- Win8: Manual (Trigger Start - DEVICE INTERFACE ARRIVAL)
- Win7: Manual

##### Proces name:

- Win8: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (bthsvcs)
- Win7: [svchost.exe -k bthsvcs](/article/winnt-services-wrapper.html) (bthsvcs)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)