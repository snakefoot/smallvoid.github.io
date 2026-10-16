---
title: 'COM+ System Application Service'
date: '2003-06-05T00:22:25+02:00'
permalink: /article/winnt-services-comsysapp.html
author: Snakefoot
excerpt: 'Description and recommended settings for the COM+ System Application service.'
type: post
id: 531
categories:
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags: []
---
##### Description:

 Manage configuration and tracking of COM+ based components.  
  
 Effects caused by disabling this service: - COM+ applications will fail to run 
  - Note COM+ applications uses the [Distributed Transaction Coordinator](/article/winnt-services-msdtc.html) to maintain transaction state, so if it is disabled then COM+ applications will also fail to run.
- COM+/OLE registration will not work
- At every boot a warning will be in the Event Log

##### Recommended State:

- Manual

##### Default State:

- Manual

##### Process Name:

- [dllhost.exe /Processid:{02D4B3F1-FD88-11D1-960D-00805FC79235}](/article/winnt-services-wrapper.html) (COMSysApp)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [COM+ Event System](/article/winnt-services-eventsystem.html)
- [System Event Notification](/article/winnt-services-sens.html) (Vista+)