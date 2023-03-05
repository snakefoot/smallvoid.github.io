---
title: 'Windows Biometric Service'
date: '2009-09-22T22:15:49+02:00'
status: publish
permalink: /article/winnt-services-wbiosrvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Biometric Service.'
type: post
id: 814
category:
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Windows biometric service gives client applications the ability to capture, compare, manipulate, and store biometric data without gaining direct access to any biometric hardware or samples. The service is hosted in a privileged SVCHOST process.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k WbioSvcGroup](/article/winnt-services-wrapper.html) (WbioSrvc)

##### Supports:

- none

##### Depends:

- [Credential Manager Service](/article/winnt-services-vaultsvc.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Windows Driver Foundation - User-mode Driver Framework](/article/winnt-services-wudfsvc.html)