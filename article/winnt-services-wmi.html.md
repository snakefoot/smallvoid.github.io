---
title: 'Windows Management Instrumentation Driver Extensions'
date: '2000-07-23T22:36:10+02:00'
status: publish
permalink: /article/winnt-services-wmi.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Management Instrumentation Driver Extensions service.'
type: post
id: 621
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wmi
post_format: []
tags:
    - wmi
---
##### Description:

 This service monitors all drivers and event trace providers that are configured to publish WMI or event trace information. If having problems with WMI, then it most likely caused by the [Windows Management Instrumentation Service](/article/winnt-services-winmgmt.html) failing to start because of a [corrupted WMI repository](/article/winnt-wmi-config.html).  
  
##### Recommended State:

- Manual, if wanting a fully functioning Windows.

##### Default State:

- Manual.

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Wmi)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Wmi)

##### Supports:

- [Background Intelligent Transfer](/article/winnt-services-bits.html) (Win2k SP3+ only)
- [Wireless Configuration](/article/winnt-services-wzcsvc.html) (Win2k SP4+ only)

##### Depends:

- None