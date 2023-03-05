---
title: 'Windows Firewall'
date: '2007-07-17T02:17:39+02:00'
status: publish
permalink: /article/winnt-services-mpssvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Firewall service.'
type: post
id: 719
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - firewall
post_format: []
tags:
    - firewall
---
##### Description:

 Helps protect your computer by preventing unauthorized users from gaining access to your computer through the Internet or a network.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalServiceNoNetwork](/article/winnt-services-wrapper.html) (MpsSvc)

##### Supports:

- none

##### Depends:

- [Base Filtering Engine](/article/winnt-services-bfe.html)