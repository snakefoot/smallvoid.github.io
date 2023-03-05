---
title: 'Smart Card Removal Policy'
date: '2007-07-17T02:16:02+02:00'
status: publish
permalink: /article/winnt-services-scpolicysvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Smart Card Removal Policy service.'
type: post
id: 700
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - smart-card
post_format: []
tags:
    - smart-card
---
##### Description:

 Allows the system to be configured to lock the user desktop upon smart card removal.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SCPolicySvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)