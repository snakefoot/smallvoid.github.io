---
title: 'Portable Device Enumerator Service'
date: '2007-07-17T02:15:35+02:00'
status: publish
permalink: /article/winnt-services-wpdbusenum.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Portable Device Enumerator Service.'
type: post
id: 694
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - media-player
post_format: []
tags:
    - media-player
---
##### Description:

 Enforces group policy for removable mass-storage devices. Enables applications such as Windows Media Player and Image Import Wizard to transfer and synchronize content using removable mass-storage devices.

##### Recommended state:

- Manual

##### Default State:

- Win8 - Manual (Trigger Start - DEVICE INTERFACE ARRIVAL)
- Win7 - Manual
- Vista - Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (WPDBusEnum)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)