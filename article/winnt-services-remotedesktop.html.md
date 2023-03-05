---
title: 'Remote Desktop Services'
date: '2009-09-20T12:01:56+02:00'
status: publish
permalink: /article/winnt-services-remotedesktop.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Desktop Services.'
type: post
id: 807
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - remote-desktop
post_format: []
tags:
    - remote-desktop
---
##### Description:

 Remote Desktop Services (aka. Terminal Services) allows multiple users to be connected interactively to the computer as they were logged on locally.  
 Remote Desktop Services also provides the feature of displaying the desktops and applications to remote computers.  
  
 The Remote Desktop Service uses by default port 3389 to listen for incoming remote control connections. This can be configured with this registry setting:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\TerminalServer \\WinStations \\RDP-Tcp\]  
> PortNumber = 3389

 Related [Remote Desktop Client](/article/windows-remote-desktop.html)  
##### Recommended State:

- Disabled, for security measures.
- Manual, if using [Remote Desktop](/article/windows-remote-desktop.html)(Remote Administration), [Remote Assistance](/article/winnt-remote-assistance.html), [Fast User Switching](/article/winnt-services-fus.html).

##### Default State:

- Manual.

##### Process Name:

- [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (TermService)

##### Supports:

- [Remote Desktop Services UserMode Port Redirector](/article/winnt-services-umrdpservice.html)
- [Media Center Extender Service](/article/winnt-services-mcx2svc.html)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)