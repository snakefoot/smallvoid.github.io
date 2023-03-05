---
title: 'Network DDE DSDM'
date: '2000-06-06T15:34:47+02:00'
status: publish
permalink: /article/winnt-services-netddedsdm.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Network DDE DSDM service.'
type: post
id: 567
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

 The DSDM(Distributed Share Database Manager), manages the shared DDE(Dynamic Data Exchange) network conversations (from shares like: \\\\computername\\ndde$).  
  
 This is mostly legacy from the old NT 3.x days, and seldom used anymore.  
  
##### Recommended State:

- Disabled, for security measures incase Network DDE shares should be configured.

##### Default State:

- WinNT4/2k/XP: Manual
- WinXP SP2: Disabled
- Win2k3: Disabled

##### Process Name:

- netdde.exe (NetDDEdsdm)

##### Supports:

- [Network DDE](/article/winnt-services-netdde.html)

##### Depends:

- None