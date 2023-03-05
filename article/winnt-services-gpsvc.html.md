---
title: 'Group Policy Client'
date: '2007-07-17T02:13:49+02:00'
status: publish
permalink: /article/winnt-services-gpsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Group Policy Client service.'
type: post
id: 672
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - group-policy
post_format: []
tags:
    - group-policy
---
##### Description:

 The service is responsible for applying settings configured by administrators for the computer and users through the Group Policy component. If the service is stopped or disabled, the settings will not be applied and applications and components will not be manageable through Group Policy. Any components or applications that depend on the Group Policy component might not be functional if the service is stopped or disabled.
 
##### Recommended state:

- Automatic

##### Default State:

- Win8: Automatic (Trigger Start - NETWORK EVENT)
- Win7/Vista: Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (gpsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)