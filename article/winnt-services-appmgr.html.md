---
title: 'Remote Server Manager'
date: '2003-09-21T15:26:25+02:00'
status: publish
permalink: /article/winnt-services-appmgr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Server Manager service.'
type: post
id: 584
category:
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 The Remote Server Manager acts as a WMI instance provider for Remote Administration Alert Objects and a WMI method provider for Remote Administration Tasks. It provides the following functionality:
- Holds the [Remote Administration Service](/article/winnt-services-srvcsurg.html) alert information.
- Provides an interface for raising, clearing, and enumerating Remote Administration Service alerts.
- Provides an interface for performing Remote Administration Service tasks.
 
 Note on non Web-edition of Windows 2003 this service can be installed by installing Remote Administration (HTML) a component of World Wide Web Service which is a module of Internet Information Server (IIS).  
  
##### Recommended State:

- Disabled, for security reasons.

##### Default State:

- Win2k3: Automatic.

##### Process Name:

- Appmgr.exe (AppMgr)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)