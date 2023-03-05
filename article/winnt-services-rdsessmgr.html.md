---
title: 'Remote Desktop Help Session Manager'
date: '2003-06-05T16:40:23+02:00'
status: publish
permalink: /article/winnt-services-rdsessmgr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Desktop Help Session Manager service.'
type: post
id: 580
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Manages and controls [Remote Assistance](/article/winnt-remote-assistance.html). If this service is stopped, Remote Assistance will be unavailable.  
  
##### Recommended State:

- Disabled, for security reasons.

##### Default State:

- WinXP: Manual.
- Win2k3: Manual.

##### Process Name:

- sessmgr.exe (RDSessMgr)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)