---
title: 'Software Licensing'
date: '2007-07-17T02:16:11+02:00'
status: publish
permalink: /article/winnt-services-slsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Software Licensing service.'
type: post
id: 702
category:
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Enables the download, installation, and enforcement of digital licenses for Windows and Windows applications. If the service is disabled, the operating system and licensed applications may run in a reduced function mode.

##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- SLsvc.exe (slsvc)

##### Supports:

- [ReadyBoost](/article/winnt-services-emdmgmt.html)
- [SL UI Notification Service](/article/winnt-services-sluinotify.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)