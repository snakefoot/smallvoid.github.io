---
title: 'Desktop Window Manager Session Manager'
date: '2007-07-17T02:12:53+02:00'
status: publish
permalink: /article/winnt-services-uxsms.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Desktop Window Manager Session Manager service.'
type: post
id: 664
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - aero
post_format: []
tags:
    - aero
---
##### Description:

 Provides Desktop Window Manager (DWM) startup and maintenance services.  
  
 This service provides the [Aero Interface effects](/article/vista-basic-aero.html) with transparent windows etc.
 
##### Recommended state:

- Automatic if wanting the Vista Aero effects.
- Disabled if wanting to save memory and like the Windows 2000 look.

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (UxSms)

##### Supports:

- none

##### Depends:

- none