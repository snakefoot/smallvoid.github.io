---
title: 'Windows Backup'
date: '2007-07-17T02:16:59+02:00'
status: publish
permalink: /article/winnt-services-sdrsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Backup service.'
type: post
id: 711
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - backup
post_format: []
tags:
    - backup
---
##### Description:

 Provides Windows Backup and Restore capabilities.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k SDRSVC](/article/winnt-services-wrapper.html) (SDRSVC)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)