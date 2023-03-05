---
title: 'MS Software Shadow Copy Provider'
date: '2003-06-05T14:18:09+02:00'
status: publish
permalink: /article/winnt-services-swprv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the MS Software Shadow Copy Provider service.'
type: post
id: 562
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - ntbackup
    - volume-shadow-copy
post_format: []
tags:
    - 'volume-shadow-copy,ntbackup'
---
##### Description:

 Manages software-based volume shadow copies taken by the [Volume Shadow Copy](/article/winnt-services-vss.html) service.  
  
 Note if the service is disable then [NTBackup](/article/winnt-ntbackup.html) will not be able to function and an error will be posted in the Event Log.  
##### Recommended State:

- Manual.

##### Default State:

- Manual.

##### Process Name:

- Win7/Vista/Win2k3: [svchost.exe -k swprv](/article/winnt-services-wrapper.html) (SwPrv)
- WinXP: [dllhost.exe /processid:{25add706-617e-4231-a770-e17fd196c466}](/article/winnt-services-wrapper.html) (SwPrv)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)