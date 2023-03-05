---
title: 'Remote Procedure Call (RPC) Locator'
date: '2000-06-06T15:18:32+02:00'
status: publish
permalink: /article/winnt-services-rpclocator.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Procedure Call Locator service.'
type: post
id: 582
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - remote-procedure-call
post_format: []
tags:
    - remote-procedure-call
---
##### Description:

 Name service provider that maintains a database with available RPC services on the server, where local RPC services can register themselves. A client can then contact the RPC locator on the server to locate and access the wanted RPC service.  
  
 This service is used by IIS to register what computers available for remote administration.  
  
 Note after installing WinXP SP2 one might get the following error:
> *Event ID: 1000  
>  RPC locator has encountered a problem and needs to be closed.*   
>  More Info [MS KB904767](http://support.microsoft.com/kb/904767 "You may receive a "RPC locator has encountered a problem and needs to be closed" error message when you install Windows XP Service Pack 2 on a computer [Q904767]")

 Note in Windows Vista and later versions of Windows, this service does not provide any functionality and is present for application compatibility.  
##### Recommended State:

- Manual (Don't confuse this service with [Remote Procedure Call](/article/winnt-services-rpcss.html))

##### Default State:

- Manual

##### Process Name:

- locator.exe (RpcLocator)

##### Supports:

- None

##### Depends:

- [Workstation](/article/winnt-services-lanmanworkstation.html) (WinXP\\Win2k\\WinNT4 only)