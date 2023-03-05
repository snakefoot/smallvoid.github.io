---
title: 'Windows Defender'
date: '2007-07-17T02:17:19+02:00'
status: publish
permalink: /article/winnt-services-windefend.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Defender service.'
type: post
id: 715
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Scans your computer for unwanted software, schedules scans, and gets the latest unwanted software definitions.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k secsvcs](/article/winnt-services-wrapper.html) (WinDefend)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)