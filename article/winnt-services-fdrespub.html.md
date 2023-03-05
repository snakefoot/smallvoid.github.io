---
title: 'Function Discovery Resource Publication'
date: '2007-07-17T02:13:45+02:00'
status: publish
permalink: /article/winnt-services-fdrespub.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Function Discovery Resource Publication service.'
type: post
id: 671
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - homegroup
    - media-center
post_format: []
tags:
    - 'media-center,homegroup'
---
##### Description:

 Publishes this computer and resources attached to this computer so they can be discovered over the network. If this service is stopped, network resources will no longer be published and they will not be discovered by other computers on the network.
 
##### Recommended state:

- Disabled if not using Windows Media Center (or Win8/Win7 Homegroup).

##### Default State:

- Manual

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (FDResPub)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (FDResPub)

##### Supports:

- [HomeGroup Provider](/article/winnt-services-homegroupprovider.html) (Win7+)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)