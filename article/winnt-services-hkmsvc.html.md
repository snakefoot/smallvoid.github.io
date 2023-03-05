---
title: 'Health Key and Certificate Management'
date: '2007-07-17T02:13:54+02:00'
status: publish
permalink: /article/winnt-services-hkmsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Health Key and Certificate Management service.'
type: post
id: 673
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - network-access-protection
post_format: []
tags:
    - network-access-protection
---
##### Description:

 Provides X.509 certificate and key management services for the [Network Access Protection Agent](/article/winnt-services-napagent.html) (NAPAgent). Enforcement technologies that use X.509 certificates may not function properly without this service.  
  
 More Info [Wiki: X.509](http://en.wikipedia.org/wiki/X.509)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7/Vista: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (hkmsvc)
- WinXP SP3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (hkmsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)