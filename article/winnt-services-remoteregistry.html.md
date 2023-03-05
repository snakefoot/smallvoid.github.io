---
title: 'Remote Registry Service'
date: '2000-07-23T15:21:57+02:00'
status: publish
permalink: /article/winnt-services-remoteregistry.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Registry service.'
type: post
id: 583
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - registry
    - remote-registry
post_format: []
tags:
    - 'remote-registry,registry'
---
##### Description:

 Allows remote registry manipulation, for authorized users.  
  
 Related [Restrict users from accessing the registry from network](/article/winnt-remote-registry.html).  
  
##### Recommended State:

- Disabled, for security measures.

##### Default State:

- Win8: Disabled.
- Vista/Win7: Manual.
- WinXP Home: Not available.
- Win2k/WinXP Pro/Win2k3: Automatic

##### Process Name:

- Win8: [svchost.exe -k localService](/article/winnt-services-wrapper.html) (RemoteRegistry)
- Win7\\Vista\\Win2k3: [svchost.exe -k regsvc](/article/winnt-services-wrapper.html) (RemoteRegistry)
- WinXP Pro: [svchost.exe -k localservice](/article/winnt-services-wrapper.html) (RemoteRegistry)
- Win2k: regsvc.exe (RemoteRegistry)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (WinXP+)