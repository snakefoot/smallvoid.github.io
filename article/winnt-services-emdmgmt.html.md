---
title: ReadyBoost
date: '2007-07-14T17:51:13+02:00'
permalink: /article/winnt-services-emdmgmt.html
author: Snakefoot
excerpt: 'Description and recommended settings for the ReadyBoost service.'
type: post
id: 698
categories:
    - 'Services Guide'
tags:
    - disk-performance
    - file-cache
    - usb
    - usb-stick
---
##### Description:

 Provides support for improving system performance using ReadyBoost.  
  
 Ready boost makes use of USB flash devices to act like an extended [hard disk cache](/article/hard-disk-cache.html). Not all USB flash devices are fast enough to act like a hard disk cache, but Vista will tell if this is the case.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (EMDMgmt)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Software Licensing](/article/winnt-services-slsvc.html)