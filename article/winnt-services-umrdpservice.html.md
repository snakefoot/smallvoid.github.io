---
title: 'Remote Desktop Services UserMode Port Redirector'
date: '2009-09-20T21:37:06+02:00'
permalink: /article/winnt-services-umrdpservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Desktop Services UserMode Port Redirector service.'
type: post
id: 808
categories:
    - 'Services Guide'
    - 'Services Guide'
tags:
    - remote-desktop
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

- [Remote Desktop Services](/article/winnt-services-remotedesktop.html)