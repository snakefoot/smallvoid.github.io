---
title: 'Storage Service'
date: '2009-09-20T23:28:38+02:00'
status: publish
permalink: /article/winnt-services-storsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Storage Service.'
type: post
id: 811
category:
    - 'Services Guide'
tag:
    - group-policy
    - removable-storage-devices
post_format: []
tags:
    - 'group-policy,removable-storage-devices'
---
##### Description:

 Enforces group policy for storage devices.
 
##### Recommended state:

- Manual

##### Default State:

- Win7 Business/Enterprise - Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (StorSvc)

##### Supports:

- none

##### Depends:

- none