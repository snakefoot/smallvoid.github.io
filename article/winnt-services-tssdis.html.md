---
title: 'Terminal Services Session Directory'
date: '2003-09-21T19:49:02+02:00'
status: publish
permalink: /article/winnt-services-tssdis.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services Session Directory service.'
type: post
id: 607
category:
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 The Terminal Services Session Directory allows clusters of load-balanced Terminal Servers to properly route a user's connection request to the server where the user already has a session running.  
  
##### Recommended State:

- Disabled.

##### Default State:

- Win2k3: Disabled.

##### Process Name:

- tssdis.exe (Tssdis)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)