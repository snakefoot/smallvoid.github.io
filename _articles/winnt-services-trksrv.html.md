---
title: 'Distributed Link Tracking Server'
date: '2000-07-23T01:12:49+02:00'
permalink: /article/winnt-services-trksrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Distributed Link Tracking Server service.'
type: post
id: 539
categories:
    - windows-2000_services
    - windows-2003_services
tags:
    - link-shortcut
    - link-tracking
---
##### Description:

 Stores information so that files moved between volumes can be tracked for each volume in the domain.  
  
 Note if disabling this service on the domain controller then the "NtfsDisableDomainLinkTracking" policy should be enabled to stop [Distributed Link Tracking Clients](/article/winnt-services-trkwks.html) from trying to reach it.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20312403%20Q312403" rel="nofollow" title="Distributed Link Tracking on Windows-Based Domain Controllers [Q312403]">MS KB312403</a>  
  
##### Recommended State:

- Disabled, if on a simple home network.
- Manual, if running a domain controller(DC).

##### Default State:

- Win2k Srv.: Manual.
- Win2k3: Disabled.

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (TrkSrv)
- Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (TrkSrv)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)