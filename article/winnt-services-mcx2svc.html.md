---
title: 'Windows Media Center Extender Service'
date: '2007-07-17T02:17:46+02:00'
status: publish
permalink: /article/winnt-services-mcx2svc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Media Center Extender Service.'
type: post
id: 720
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - media-center
post_format: []
tags:
    - media-center
---
##### Description:

 Allows Windows Media Center Extender devices to locate and connect to the computer.  
  
 The Windows Media Center Extender service makes it possible to connect devices over the network, so they can stream audio and video from the computer. This can be used to connect a XBox 360, which then can be used to browse the movies and music on the computer and to play/show it on the attached TV.
 
##### Recommended state:

- Disabled

##### Default State:

- Win8 Pro: Disabled
- Win7 Premium/Pro: Disabled
- Vista Premium/Ultimate: Disabled

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (Mcx2Svc)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (Mcx2Svc)

##### Supports:

- none

##### Depends:

- [Function Discovery Provider Host](/article/winnt-services-fdphost.html)
- [PnP-X IP Bus Enumerator](/article/winnt-services-ipbusenum.html)
- [SSDP Discovery](/article/winnt-services-ssdpsrv.html)
- [Remote Desktop Services](/article/winnt-services-remotedesktop.html) (Win7+)
- [Terminal Services](/article/winnt-services-termservice.html) (Vista only)