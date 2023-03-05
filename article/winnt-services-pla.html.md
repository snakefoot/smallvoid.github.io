---
title: 'Performance Logs &amp; Alerts'
date: '2007-07-17T02:15:21+02:00'
status: publish
permalink: /article/winnt-services-pla.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Performance Logs &amp; Alerts service.'
type: post
id: 691
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - performance-counters
    - performance-monitor
post_format: []
tags:
    - 'performance-monitor,performance-counters'
---
##### Description:

 Performance Logs and Alerts Collects performance data from local or remote computers based on preconfigured schedule parameters, then writes the data to a log or triggers an alert. If this service is stopped, performance information will not be collected.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (pla)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)