---
title: 'Windows Audio Endpoint Builder'
date: '2007-07-17T02:16:48+02:00'
status: publish
permalink: /article/winnt-services-audioendpointbuilder.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Audio Endpoint Builder service.'
type: post
id: 710
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Manages audio devices for the Windows Audio service. If this service is stopped, audio devices and effects will not function properly. If this service is disabled, any services that explicitly depend on it will fail to start.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (AudioEndpointBuilder)

##### Supports:

- [Windows Audio](/article/winnt-services-audiosrv.html)

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)