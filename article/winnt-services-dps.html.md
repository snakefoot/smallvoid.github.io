---
title: 'Diagnostic Policy Service'
date: '2007-07-17T02:13:20+02:00'
status: publish
permalink: /article/winnt-services-dps.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Diagnostic Policy Service.'
type: post
id: 666
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Diagnostic Policy Service service enables problem detection, troubleshooting and resolution for Windows components. If this service is stopped, some diagnostics will no longer function. If this service is disabled, any services that explicitly depend on it will fail to start.  
  
 Part of the Windows Diagnostics Infrastructure (WDI) framework.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (DPS)

##### Supports:

- none

##### Depends:

- none