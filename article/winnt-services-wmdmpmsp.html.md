---
title: 'WMDM PMSP Service / Portable Media Serial Number'
date: '2000-07-23T23:52:13+02:00'
status: publish
permalink: /article/winnt-services-wmdmpmsp.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Portable Media Serial Number service.'
type: post
id: 625
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - drm
    - windows-media-player
post_format: []
tags:
    - 'windows-media-player,drm'
---
##### Description:

 The service supports the Secure Digital Music Initiative(SDMI) and enables the WMDM (Windows Media Device Manager) to retrieve the serial number from portable music devices using Pre-Message Security Protocol(PMSP), so media content can be copied securely to the device.  
  
 If not being able to extract the serial number from the device (If this service is disabled or the device doesn't support it), then copyrighted music will not be allowed to be transferred to the device.  
  
##### Recommended State:

- Manual.

##### Default State:

- Win2k/WinXP: Automatic.
- WinXP SP2: Manual.
- Win2k3: Manual.

##### Process Name:

- Win2k WMP 7.1+: MsPMSPSv.exe (WMDM PMSP Service)
- WinXP/2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (WmdmPmSp)

##### Supports:

- None

##### Depends:

- None