---
title: 'SPP Notification Service'
date: '2009-09-20T23:18:21+02:00'
status: publish
permalink: /article/winnt-services-sppuinotify.html
author: Snakefoot
excerpt: 'Description and recommended settings for the SPP Notification Service.'
type: post
id: 810
category:
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides Software Licensing (SL) activation and notification.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (SLUINotify)

##### Supports:

- none

##### Depends:

- [COM+ Event System](/article/winnt-services-eventsystem.html)