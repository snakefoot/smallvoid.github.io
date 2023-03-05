---
title: 'RPC Endpoint Mapper'
date: '2009-09-20T22:41:40+02:00'
status: publish
permalink: /article/winnt-services-rpceptmapper.html
author: Snakefoot
excerpt: 'Description and recommended settings for the RPC Endpoint Mapper service.'
type: post
id: 809
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - remote-procedure-call
post_format: []
tags:
    - remote-procedure-call
---
##### Description:

 Resolves RPC interfaces identifiers to transport endpoints. If this service is stopped or disabled, programs using Remote Procedure Call (RPC) services will not function properly.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k RPCSS](/article/winnt-services-wrapper.html) (RpcEptMapper)

##### Supports:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Local Session Manager](/article/winnt-services-lsm.html) (Win8+)
- [Background Tasks Infrastructure Service](/article/winnt-services-brokerinfrastructure.html) (Win8+)

##### Depends:

- none