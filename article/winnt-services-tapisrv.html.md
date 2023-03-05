---
title: Telephony
date: '2000-06-06T19:21:04+02:00'
status: publish
permalink: /article/winnt-services-tapisrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Telephony service.'
type: post
id: 603
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dialup-modem
    - tapi
post_format: []
tags:
    - 'tapi,dialup-modem'
---
##### Description:

 It provides Telephony API (TAPI) support for programs that control telephony devices. The telephony service enables applications to act as clients to telephony equipment such as PBXs, telephones, and modems.  
  
 It can also be used to IP based voice connections on the local computer and, through the LAN. Though it requires that the other computers also is running this service.  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- Win2k/WinXP: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (TapiSrv)
- Win2k3: [svchost.exe -k tapisrv](/article/winnt-services-wrapper.html) (TapiSrv)
- Vista/Win7: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (TapiSrv)

##### Supports:

- [FAX Service](/article/winnt-services-fax.html)
- [Remote Access Auto Connection Manager](/article/winnt-services-rasauto.html)
- [Remote Access Connection Manager](/article/winnt-services-rasman.html)

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)