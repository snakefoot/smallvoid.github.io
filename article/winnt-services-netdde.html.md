---
title: 'Network DDE'
date: '2000-06-06T15:31:20+02:00'
status: publish
permalink: /article/winnt-services-netdde.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network DDE service.'
type: post
id: 566
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

 Supports network transport and security of DDE (Dynamic Data Exchange) connections.  
  
 This is mostly legacy from the old NT 3.x days, and seldom used anymore.  
  
 To access the configuration of the DDE Shares run this command:
 > %windir%/system32/ddeshare.exe

##### Recommended State:

- Disabled, for security measures incase Network DDE shares should be configured.

##### Default State:

- WinNT4/2k/XP: Manual
- WinXP SP2: Disabled
- Win2k3: Disabled

##### Process Name:

- netdde.exe (NetDDE)

##### Supports:

- [Clipbook Server](/article/winnt-services-clipsrv.html)

##### Depends:

- [Network DDE DSDM](/article/winnt-services-netddedsdm.html)