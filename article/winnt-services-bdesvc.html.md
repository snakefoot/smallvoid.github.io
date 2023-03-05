---
title: 'BitLocker Drive Encryption Service'
date: '2009-09-16T10:53:45+02:00'
status: publish
permalink: /article/winnt-services-bdesvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the BitLocker Drive Encryption Service.'
type: post
id: 796
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - bitlocker
    - encryption
    - file-system
post_format: []
tags:
    - 'bitlocker,encryption'
---
##### Description:

 BDESVC hosts the BitLocker Drive Encryption service. BitLocker Drive Encryption provides secure startup for the operating system, as well as full volume encryption for OS, fixed or removable volumes. This service allows BitLocker to prompt users for various actions related to their volumes when mounted, and unlocks volumes automatically without user interaction. Additionally, it stores recovery information to Active Directory, if available, and, if necessary, ensures the most recent recovery certificates are used. Stopping or disabling the service would prevent users from leveraging this functionality.  
##### Recommended state:

- Manual

##### Default State:

- Win8: Manual (Trigger Start)
- Win7: Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (BDESVC)

##### Supports:

- none

##### Depends:

- none