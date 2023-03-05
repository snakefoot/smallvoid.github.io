---
title: Clipbook
date: '2000-06-06T00:00:49+02:00'
status: publish
permalink: /article/winnt-services-clipsrv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Clipbook service.'
type: post
id: 527
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - network-dde
post_format: []
tags:
    - network-dde
---
##### Description:

 Is used to access the machine's clipboard remotely using the NetDDE service.  
  
 It is an old service from the NT 3.X days.  
  
 Note Acrobat Reader has a menu option Window -&gt; "Show Clipboard", which starts the Clipboard Viewer in Windows (Can be installed through Add/Remove Programs in Control Panel). Windows Clipboard Viewer uses this service and will fail to operate if it is disabled.  
  
##### Recommended State:

- Disabled, for security measures.

##### Default State:

- Win2k: Manual.
- WinXP: Manual.
- WinXP SP2: Disabled.
- Win2k3: Disabled.

##### Process Name:

- clipsrv.exe (ClipSrv)

##### Supports:

- None

##### Depends:

- [Network DDE](/article/winnt-services-netdde.html)