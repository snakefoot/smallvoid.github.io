---
title: 'Link-Layer Topology Discovery Mapper'
date: '2007-07-17T02:14:19+02:00'
status: publish
permalink: /article/winnt-services-lltdsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Link-Layer Topology Discovery Mapper service.'
type: post
id: 678
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Creates a Network Map, consisting of PC and device topology (connectivity) information, and metadata describing each PC and device. If this service is disabled, the Network Map will not function properly.  
  
 More Info [Wiki: Link Layer Topology Discovery](http://en.wikipedia.org/wiki/Link_Layer_Topology_Discovery)  
  
 Related [Link Layer Topology Discovery (LLTD) Responder for WinXP](/article/winxp-lltd-responder.html)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (lltdsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)