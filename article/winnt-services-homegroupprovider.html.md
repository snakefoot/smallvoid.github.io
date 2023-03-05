---
title: 'HomeGroup Provider'
date: '2009-09-18T19:48:48+02:00'
status: publish
permalink: /article/winnt-services-homegroupprovider.html
author: Snakefoot
excerpt: 'Description and recommended settings for the HomeGroup Provider service.'
type: post
id: 802
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

 Performs networking tasks associated with configuration and maintenance of homegroups. If this service is stopped or disabled, your computer will be unable to detect other homegroups and your homegroup might not work properly. It is recommended that you keep this service running.
 
##### Recommended state:

- Manual

##### Default State:

- Win8: Manual (Trigger Start)
- Win7: Manual

##### Proces name:

- [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (HomeGroupProvider)

##### Supports:

- none

##### Depends:

- [Function Discovery Provider Host ](/article/winnt-services-fdphost.html)
- [Function Discovery Resource Publication ](/article/winnt-services-fdrespub.html)
- [Network List Service](/article/winnt-services-netprofm.html)