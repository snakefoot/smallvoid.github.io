---
title: 'WWAN AutoConfig'
date: '2009-09-22T23:21:10+02:00'
status: publish
permalink: /article/winnt-services-wwansvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the WWAN AutoConfig Service.'
type: post
id: 815
category:
    - 'Services Guide'
tag:
    - GSM
post_format: []
tags:
    - GSM
---
##### Description:

 This service manages mobile broadband (GSM &amp; CDMA) data card/embedded module adapters and connections by auto-configuring the networks. It is strongly recommended that this service be kept running for best user experience of mobile broadband devices. 
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (WwanSvc)

##### Supports:

- none

##### Depends:

- [Network Location Awareness](/article/winnt-services-nla.html)
- [Plug and Play](/article/winnt-services-plugplay.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)