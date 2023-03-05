---
title: 'Windows Media Center Service Launcher'
date: '2007-07-17T02:18:01+02:00'
status: publish
permalink: /article/winnt-services-ehstart.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Media Center Service Launcher service.'
type: post
id: 723
category:
    - 'Services Guide'
tag:
    - media-center
post_format: []
tags:
    - media-center
---
##### Description:

 Starts Windows Media Center Scheduler and Windows Media Center Receiver services at startup if TV is enabled within Windows Media Center.
 
##### Recommended state:

- Disabled if not using Windows Media Center.

##### Default State:

- Vista Home Basic: Not Available
- Vista Home Premium: Automatic (Delayed Start)
- Vista Home Business: Not Installed
- Vista Home Ultimate: Automatic (Delayed Start)

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (ehstart)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)