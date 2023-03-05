---
title: 'Terminal Services UserMode Port Redirector'
date: '2007-07-17T02:16:34+02:00'
status: publish
permalink: /article/vista-services-umrdpservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Terminal Services UserMode Port Redirector service.'
type: post
id: 706
category:
    - 'Services Guide'
tag:
    - remote-desktop
post_format: []
tags:
    - remote-desktop
---
##### Description:

 Allows the redirection of printers/drives/ports for Remote Desktop Protocol (RDP) connections.
 
##### Recommended state:

- Manual if using [Remote Desktop](/article/windows-remote-desktop.html)
- Disabled for security measures

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (UmRdpService)

##### Supports:

- none

##### Depends:

- [Terminal Services](/article/winnt-services-termservice.html)