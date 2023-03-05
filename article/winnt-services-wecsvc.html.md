---
title: 'Windows Event Collector'
date: '2007-07-17T02:17:34+02:00'
status: publish
permalink: /article/winnt-services-wecsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Event Collector service.'
type: post
id: 718
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - event-log
post_format: []
tags:
    - event-log
---
##### Description:

 Manages persistent subscriptions to events from remote sources that support the WS-Management protocol. This includes Windows Vista event logs, hardware, and IPMI-enabled event sources. If this service is stopped or disabled, event subscriptions cannot be created and forwarded events cannot be accepted.  
  
 More Info [MSDN - Windows Event Collector](http://msdn2.microsoft.com/en-us/library/bb427443.aspx).
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (Wecsvc)

##### Supports:

- none

##### Depends:

- [Windows Event Log](/article/winnt-services-eventlog.html) (Win7+)