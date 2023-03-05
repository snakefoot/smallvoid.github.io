---
title: 'Function Discovery Provider Host'
date: '2007-07-17T02:13:40+02:00'
status: publish
permalink: /article/winnt-services-fdphost.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Function Discovery Provider Host service.'
type: post
id: 670
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - homegroup
    - media-center
post_format: []
tags:
    - 'media-center,homegroup'
---
##### Description:

 The FDPHOST service hosts the Function Discovery (FD) network discovery providers. These FD providers supply network discovery services for the Simple Services Discovery Protocol (SSDP) and Web Services – Discovery (WS-D) protocol. Stopping or disabling the FDPHOST service will disable network discovery for these protocols when using FD. When this service is unavailable, network services using FD and relying on these discovery protocols will be unable to find network devices or resources.  
  
 Allows resources to be discovered over the network. This could forexample be a Media Center Extender (Like the XBOX that can stream media from the computer), or a printer attached over the network.
 
##### Recommended state:

- Disabled if not using Windows Media Center (or Win8/Win7 homegroup).

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (fdPHost)

##### Supports:

- [HomeGroup Provider](/article/winnt-services-homegroupprovider.html) (Win7+)
- [Windows Media Center Extender Service](/article/winnt-services-mcx2svc.html)
- [PnP-X IP Bus Enumerator](/article/winnt-services-ipbusenum.html) (Vista/Win7 only)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)