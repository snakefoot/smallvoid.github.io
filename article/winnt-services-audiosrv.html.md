---
title: 'Windows Audio'
date: '2003-06-05T21:29:09+02:00'
status: publish
permalink: /article/winnt-services-audiosrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Audio service.'
type: post
id: 616
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Manages audio devices for Windows-based programs.  
##### Recommended State:

- Automatic, if you like sound.

##### Default State:

- WinXP: Automatic
- Win2k3 Std.: Automatic
- Win2k3 Enterprise/Datacenter/Web: Disabled.
- Vista/Win7: Automatic

##### Process Name:

- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AudioSrv)
- Vista: [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (AudioSrv)

##### Supports:

- None

##### Depends:

- [Multimedia Class Scheduler](/article/winnt-services-mmcss.html) (Vista+)
- [Plug and Play](/article/winnt-services-plugplay.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Windows Audio Endpoint Builder](/article/winnt-services-audioendpointbuilder.html) (Vista+)