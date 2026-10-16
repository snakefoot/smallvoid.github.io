---
title: 'Remote Desktop Configuration'
date: '2009-09-19T12:11:56+02:00'
permalink: /article/winnt-services-sessionenv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Desktop Configuration service (RDCS).'
type: post
id: 806
categories:
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - remote-desktop
---
##### Description:

 Remote Desktop Configuration service (RDCS) is responsible for all Remote Desktop Services and Remote Desktop related configuration and session maintenance activities that require SYSTEM context. These include per-session temporary folders, RD themes, and RD certificates.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SessionEnv)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)