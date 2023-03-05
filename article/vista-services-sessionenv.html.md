---
title: 'Terminal Services Configuration'
date: '2007-07-17T02:16:29+02:00'
status: publish
permalink: /article/vista-services-sessionenv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services Configuration service (TSCS).'
type: post
id: 705
category:
    - 'Services Guide'
tag:
    - remote-desktop
post_format: []
tags:
    - remote-desktop
---
##### Description:

 Terminal Services Configuration service (TSCS) is responsible for all Terminal Services and Remote Desktop related configuration and session maintenance activities that require SYSTEM context. These include per-session temporary folders, TS themes, and TS certificates.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SessionEnv)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)