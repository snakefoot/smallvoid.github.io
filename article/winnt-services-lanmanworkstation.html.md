---
title: Workstation
date: '2000-06-06T00:02:04+02:00'
status: publish
permalink: /article/winnt-services-lanmanworkstation.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Workstation service.'
type: post
id: 627
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - microsoft-network
post_format: []
tags:
    - microsoft-network
---
##### Description:

 The workstation service is a user-mode wrapper for the Microsoft Networks redirector. Both local file system requests and remote file or print network requests are routed through the Workstation service. This service determines where the resource is located and then routes the request to the local file system or to the networking components.  
  
 Disabling this service will have following side-effects:
- Will stop all outgoing share communication, and block access to shared resources (Files/Printers)
- Will disable use of UNC paths.
- Any service dependent on this service will also fail leaving errors in the Event Log.
 
 Note if wanting the functionality of this service on the local machine, but doesn't want it to access the network, then it can be a good idea to have the network component "Client for Microsoft Networks network" installed, but not attached to the installed network-adapter.  
  
 More Info [MS KB197157](http://support.microsoft.com/kb/197157 "Workstation Service Does Not Start [Q197157]")  
  
##### Recommended State:

- Automatic, when in a simple home network.
- Disabled, if not needing access to network-shares, to disable uninstall the network component "Client for Microsoft Networks network".

##### Default State:

- Automatic

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (lanmanworkstation)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (lanmanworkstation)

##### Supports:

- [Alerter](/article/winnt-services-alerter.html) (WinNT4/Win2k/WinXP/Win2k3 only)
- [Background Intelligent Transfer](/article/winnt-services-bits.html) (Win2k SP3+ only)
- [Computer Browser](/article/winnt-services-browser.html)
- [Distributed File System](/article/winnt-services-dfs.html) (Win2k/Win2k3 only)
- [Messenger](/article/winnt-services-messenger.html) (WinNT4/Win2k/WinXP/Win2k3 only)
- [NET Logon](/article/winnt-services-netlogon.html)
- [Remote Procedure Call (RPC) Locator](/article/winnt-services-rpclocator.html) (WinNT4/Win2k/WinXP/Win2k3 only)
- [Remote Desktop Configuration](/article/winnt-services-sessionenv.html) (Win7+)
- [Terminal Services Configuration](/article/vista-services-sessionenv.html) (Vista only)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html) (Vista+)