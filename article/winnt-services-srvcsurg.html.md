---
title: 'Remote Administration Service'
date: '2003-09-21T16:37:59+02:00'
status: publish
permalink: /article/winnt-services-srvcsurg.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Administration service.'
type: post
id: 579
category:
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Remote Administration Service is responsible for performing the following remote administration tasks when Windows restarts:
- Increment the server boot count.
- Send an alert when the computer is running a backup of the operating system.
- Generate a self-signed certificate.
- Send an alert if the date and time has not been set on the computer.
- Send an alert if Alert E-mail functionality has not been configured.

##### Recommended State:

- Disabled, for security reasons.

##### Default State:

- Win2k3: Automatic.

##### Process Name:

- srvcsurg.exe (SrvcSurg)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)