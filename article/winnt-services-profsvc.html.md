---
title: 'User Profile Service'
date: '2007-07-17T02:16:53+02:00'
status: publish
permalink: /article/winnt-services-profsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the User Profile Service.'
type: post
id: 709
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - user-account-control
post_format: []
tags:
    - user-account-control
---
##### Description:

 Responsible for loading and unloading user profiles. If this service is stopped or disabled, users will no longer be able to successfully log on or log off, applications may have problems getting to users' data, and components registered to receive profile event notifications will not receive them.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (ProfSvc)

##### Supports:

- [Application Information](/article/winnt-services-aelookupsvc.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)