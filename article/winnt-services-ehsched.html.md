---
title: 'Windows Media Center Scheduler Service'
date: '2007-07-17T02:17:55+02:00'
status: publish
permalink: /article/winnt-services-ehsched.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Media Center Scheduler Service.'
type: post
id: 722
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - media-center
post_format: []
tags:
    - media-center
---
##### Description:

 Starts and stops recording of TV programs within Windows Media Center.
 
##### Recommended state:

- Disabled if not using Windows Media Center.

##### Default State:

- Vista Home Basic: Not Available
- Vista Home Premium: Manual
- Vista Home Business: Not Installed
- Vista Home Ultimate: Manual
- Win7 Premium/Business/Ultimate: Manual

##### Proces name:

- ehsched.exe (ehSched)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)