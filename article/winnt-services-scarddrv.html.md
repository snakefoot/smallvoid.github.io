---
title: 'Smart Card Helper'
date: '2000-07-23T18:54:40+02:00'
status: publish
permalink: /article/winnt-services-scarddrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Smart Card Helper service.'
type: post
id: 597
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - smart-card
post_format: []
tags:
    - smart-card
---
##### Description:

 Provides support for legacy smart card readers attached to the computer.  
  
 Note with WinXP SP2+ and Win2k3 the functionality provided by this service have been moved into [Smart Card](/article/winnt-services-scardsvr.html) and this service is no more.  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- SCardSvr.exe (SCardDrv)

##### Supports:

- None

##### Depends:

- None