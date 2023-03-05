---
title: 'COM+ Event System'
date: '2000-07-23T00:10:59+02:00'
status: publish
permalink: /article/winnt-services-eventsystem.html
author: Snakefoot
excerpt: 'Description and recommended settings for the COM+ Event System service.'
type: post
id: 529
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides automatic distribution of events to COM+ components.  
  
 Note if disabling this service then at every boot there will be generated a warning in the Event Log about this service not running.  
  
 Note in WinXP the [prefetching](/article/winnt-logical-prefetcher.html) and [bootvis](/article/winxp-bootvis.html) are dependent on this service.  
  
 Related [How to repair a broken COM+ catalog and reinstall COM+](/article/winnt-com-event-system-config.html)  
  
##### Recommended State:

- Automatic

##### Default State:

- Win8/Win7/Vista: Automatic
- WinXP/Win2k/WinNT4: Manual

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (EventSystem)
- WinXP/Win2k/WinNT4: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (EventSystem)

##### Supports:

- [Background Intelligent Transfer Service](/article/winnt-services-bits.html) (Vista+)
- [COM+ System Application](/article/winnt-services-comsysapp.html) (WinXP+)
- [System Event Notification Service (SENS)](/article/winnt-services-sens.html)
- [File Replication](/article/winnt-services-ntfrs.html) (Win2k3+)
- [DFS Replication](/article/winnt-services-dfsr.html) (Win2k8)
- [SL UI Notification Service](/article/winnt-services-sluinotify.html) (Vista)
- [SPP Notification Service ](/article/winnt-services-sppuinotify.html) (Win7)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)