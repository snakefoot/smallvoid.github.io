---
title: 'Application Identity'
date: '2009-09-16T01:26:18+02:00'
status: publish
permalink: /article/winnt-services-appidsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Application Identity Service.'
type: post
id: 795
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - applocker
post_format: []
tags:
    - applocker
---
##### Description:

 Determines and verifies the identity of an application. Disabling this service will prevent AppLocker from being enforced.
 
##### Recommended state:

- Windows 8: Manual (Trigger Start)
- Windows 7: Manual

##### Default State:

- Windows 8: Manual (Trigger Start)
- Windows 7: Manual

##### Proces name:

- [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (AppIDSvc)

##### Supports:

- None

##### Depends:

- [Cryptographic Services](/article/winnt-services-cryptsvc.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)