---
title: 'SL UI Notification Service'
date: '2007-07-17T02:15:53+02:00'
permalink: /article/winnt-services-sluinotify.html
author: Snakefoot
excerpt: 'Description and recommended settings for the SL UI Notification Service.'
type: post
id: 699
categories:
    - windows-vista-services-guide
tags: []
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
- [Network List Service](/article/winnt-services-netprofm.html)
- [Software Licensing](/article/winnt-services-slsvc.html)