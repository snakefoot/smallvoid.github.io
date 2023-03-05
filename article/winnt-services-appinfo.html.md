---
title: 'Application Information'
date: '2007-07-17T02:10:37+02:00'
status: publish
permalink: /article/winnt-services-appinfo.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Application Information Service (AIS).'
type: post
id: 659
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - user-account-control
post_format: []
tags:
    - user-account-control
---
##### Description:

 Facilitates the running of interactive applications with additional administrative privileges. If this service is stopped, users will be unable to launch applications with the additional administrative privileges they may require to perform desired user tasks.  
  
 Used by [User Account Protection](/article/winnt-user-account-protection.html) to elevate applications to have Administrator privileges. Disabling this service will prevent tools like regedit from being able to make any changes. Re-enable this service by booting in safemode.  
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Appinfo)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [User Profile Service](/article/winnt-services-profsvc.html)