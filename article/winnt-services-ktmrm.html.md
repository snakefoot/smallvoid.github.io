---
title: 'KtmRm for Distributed Transaction Coordinator'
date: '2007-07-17T02:14:09+02:00'
status: publish
permalink: /article/winnt-services-ktmrm.html
author: Snakefoot
excerpt: 'Description and recommended settings for the KtmRm for Distributed Transaction Coordinator service.'
type: post
id: 677
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Coordinates transactions between the [Distributed Transaction Coordinator](/article/winnt-services-msdtc.html) (MSDTC) and the Kernel Transaction Manager (KTM).  
  
 MSDTC focuses on COM+ components, MSMQ and database transactions, while KTM focuses on registry and NTFS filesystem transactions.  
  
 More Info [Wiki: Kernel Transaction Manager](http://en.wikipedia.org/wiki/Kernel_Transaction_Manager)
 
##### Recommended state:

- Manual

##### Default State:

- Win8 - Manual (Trigger Start)
- Win7 - Manual
- Vista - Automatic (Delayed Start)

##### Proces name:

- Win8/Win7 - [svchost.exe -k NetworkServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (KtmRM)
- Vista - [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (KtmRM)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Security Accounts Manager](/article/winnt-services-samss.html)