---
title: 'Network Provisioning Service'
date: '2004-09-12T15:40:47+02:00'
status: publish
permalink: /article/winnt-services-xmlprov.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network Provisioning service.'
type: post
id: 569
category:
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Manages XML configuration files on a domain basis for automatic network provisioning.  
  
##### Recommended State:

- Manual.

##### Default State:

- WinXP SP2: Manual.

##### Process Name:

- WinXP SP2: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (xmlprov)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)