---
title: 'HTTP SSL / SSL for HTTP.SYS'
date: '2003-09-21T02:03:58+02:00'
status: publish
permalink: /article/winnt-services-httpfilter.html
author: Snakefoot
excerpt: 'Description and recommended settings for the HTTP SSL service.'
type: post
id: 549
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 This service implements the secure hypertext transfer protocol (HTTPS) for the HTTP service, using the Secure Socket Layer (SSL). SSL is a proposed open standard for establishing a secure communications channel to prevent the interception of critical information, such as credit card numbers.  
  
 Note if this service is disabled then any HTTP request aimed for the Internet Information Services (IIS) will not be handled.  
  
##### Recommended State:

- Manual.

##### Default State:

- WinXP SP2: Manual
- Win2k3: Manual

##### Process Name:

- Win2k3: [lsass.exe](/article/winnt-services-wrapper.html) (HTTPFilter)
- WinXP SP2: [svchost.exe -k HTTPFilter](/article/winnt-services-wrapper.html) (HTTPFilter)

##### Supports:

- None

##### Depends:

- IIS Admin Service (Win2k3 only)
- HTTP Driver (If IIS installed)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Security Accounts Manager](/article/winnt-services-samss.html)