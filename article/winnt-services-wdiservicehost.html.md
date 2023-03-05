---
title: 'Diagnostic Service Host'
date: '2007-07-17T02:13:31+02:00'
status: publish
permalink: /article/winnt-services-wdiservicehost.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Diagnostic Service Host service.'
type: post
id: 668
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Diagnostic Service Host service enables problem detection, troubleshooting and resolution for Windows components. If this service is stopped, some diagnostics will no longer function. If this service is disabled, any services that explicitly depend on it will fail to start.  
  
 Part of the Windows Diagnostics Infrastructure (WDI) framework.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (WdiServiceHost)
- Vista: [svchost.exe -k wdisvc](/article/winnt-services-wrapper.html) (WdiServiceHost)

##### Supports:

- none

##### Depends:

- none