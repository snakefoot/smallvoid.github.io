---
title: 'Quality Windows Audio Video Experience'
date: '2007-07-17T02:15:49+02:00'
status: publish
permalink: /article/winnt-services-qwave.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Quality Windows Audio Video Experience service.'
type: post
id: 697
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Quality Windows Audio Video Experience (qWave) is a networking platform for Audio Video (AV) streaming applications on IP home networks. qWave enhances AV streaming performance and reliability by ensuring network quality-of-service (QoS) for AV applications. It provides mechanisms for admission control, run time monitoring and enforcement, application feedback, and traffic prioritization.  
  
 More Info [MS WHDC - qWave](http://www.microsoft.com/whdc/device/stream/qWave.mspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (QWAVE)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (QWAVE)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)