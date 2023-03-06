---
title: 'Parental Controls'
date: '2007-07-17T02:15:02+02:00'
status: publish
permalink: /article/winnt-services-wpcsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Parental Controls service.'
type: post
id: 687
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - parental-control
post_format: []
tags:
    - parental-control
---
##### Description:

 This service enables Windows Parental Controls on the system. If this service is not running, Parental controls will not work.  
  
 Parental control enables functions like:
- Restrict what games/programs that can be started.
- Restrict what websites that can be visited.
- Enforce time limits for how many hours a day the computer can be used.
- Monitor activity report of what the computer was used for.
 
 More Info [Vista - Explore the features: Parental controls](http://www.microsoft.com/windows/windows-vista/features/parental-controls.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Vista Home/Ultimate: Manual
- Vista Business: Not installed
- Win7: Manual

##### Proces name:

- [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (WPCSvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)