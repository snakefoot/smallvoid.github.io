---
title: 'WMI Performance Adapter'
date: '2003-06-05T23:56:15+02:00'
status: publish
permalink: /article/winnt-services-wmiapsrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the WMI Performance Adapter service.'
type: post
id: 626
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wmi
post_format: []
tags:
    - wmi
---
##### Description:

 Provides performance library information from WMI (Windows Management Instrumentation) HiPerf providers to Performance Data Helper (PDH) clients.  
  
 Note if getting errors about WMI then it is most likely a problem with the [Windows Management Instrumentation Service](/article/winnt-services-winmgmt.html).  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual.

##### Process Name:

- wmiapsrv.exe (WmiApSrv)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (WinXP/Win2k3 only)