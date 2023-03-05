---
title: 'HomeGroup Listener'
date: '2009-09-18T19:42:54+02:00'
status: publish
permalink: /article/winnt-services-homegrouplistener.html
author: Snakefoot
excerpt: 'Description and recommended settings for the HomeGroup Listener service.'
type: post
id: 801
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - homegroup
post_format: []
tags:
    - homegroup
---
##### Description:

 Makes local computer changes associated with configuration and maintenance of the homegroup-joined computer. If this service is stopped or disabled, your computer will not work properly in a homegroup and your homegroup might not work properly. It is recommended that you keep this service running.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (HomeGroupListener)

##### Supports:

- none

##### Depends:

- [Server](/article/winnt-services-lanmanserver.html) (Win7 only)