---
title: 'Program Compatibility Assistant Service'
date: '2007-07-17T02:15:44+02:00'
status: publish
permalink: /article/winnt-services-pcasvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Program Compatibility Assistant Service.'
type: post
id: 696
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - application-compatibility
    - user-account-protection
post_format: []
tags:
    - 'application-compatibility,user-account-protection'
---
##### Description:

 Provides support for the Program Compatibility Assistant. If this service is stopped, the Program Compatibility Assistant will not function properly. If this service is disabled, any services that depend on it will fail to start.  
  
 The Program Compatibility Assistant (PCA) detects when an older program has compatibility problems, and then automatically tries to apply the proper compatibility settings: - [User Account Protection](/article/winnt-user-account-protection.html) (UAP) might block an application from working properly as it requires Administrator rights. PCA will automatically elevate the application if needed and display the UAP prompt.
- If an application tries to install an unsigned driver on 64 bit Windows, then PCA will disable the driver automatically as Windows will not load if an unsigned driver is detected.
 
 If the PCA cannot determine the needed settings, then it will prompt the user for what action to take. More Info [MS Windows Help - Program Compatibility Assistant FAQ](http://windowshelp.microsoft.com/Windows/en-US/Help/82c0440d-553e-47e9-b4bd-6c2d10df4de71033.mspx).
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (PcaSvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)