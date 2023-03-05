---
title: 'Diagnostic System Host'
date: '2007-07-17T02:13:25+02:00'
status: publish
permalink: /article/winnt-services-wdisystemhost.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Diagnostic System Host service.'
type: post
id: 667
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Diagnostic System Host service enables problem detection, troubleshooting and resolution for Windows components. If this service is stopped, some diagnostics will no longer function. If this service is disabled, any services that explicitly depend on it will fail to start.  
  
 Part of the Windows Diagnostics Infrastructure (WDI) framework.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (WdiSystemHost)

##### Supports:

- none

##### Depends:

- none