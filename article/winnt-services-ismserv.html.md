---
title: 'Intersite Messaging'
date: '2000-07-23T02:24:02+02:00'
status: publish
permalink: /article/winnt-services-ismserv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Intersite Messaging service.'
type: post
id: 554
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Allows sending and receiving messages between Windows Advanced Server sites. This service is used for mail-based replication between sites. Active Directory includes support for replication between sites by using SMTP over IP.  
  
##### Recommended State:

- Disabled, if on a simple home network.

##### Default State:

- Disabled

##### Process Name:

- ismserv.exe (IsmServ)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (Win2k3)
- [Security Accounts Manager](/article/winnt-services-samss.html)