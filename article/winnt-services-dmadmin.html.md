---
title: 'Logical Disk Manager Administrative Service'
date: '2000-07-23T14:11:07+02:00'
status: publish
permalink: /article/winnt-services-dmadmin.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Logical Disk Manager Administrative service.'
type: post
id: 560
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Administrative service for disk management requests. This service is started only when configuring a drive or partition or when a new drive is detected.  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- dmadmin.exe (dmadmin)

##### Supports:

- None

##### Depends:

- [Logical Disk Manager](/article/winnt-services-dmserver.html) (WinXP only)
- [Plug and Play](/article/winnt-services-plugplay.html) (WinXP only)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (WinXP only)