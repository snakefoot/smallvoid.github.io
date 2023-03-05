---
title: 'System Event Notification'
date: '2000-06-06T19:04:14+02:00'
status: publish
permalink: /article/winnt-services-sens.html
author: Snakefoot
excerpt: 'Description and recommended settings for the System Event Notification service (SENS).'
type: post
id: 600
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

 System Event Notification Service(SENS) tracks system events such as Windows logon, network, and power events. Notifies COM+ Event System subscribers of these events.  
  
 If disabling the service it will have the following effects:
- A warning is posted in the Event Log at every boot.
- Win32 APIs IsNetworkAlive() and IsDestinationReachable() will not work. These are mostly used by mobile applications and on portable computers.
- SENS interfaces will not work properly. In particular, SENS' Logon/Logoff notifications will not work.
- SyncMgr (Mobsync.exe) will not work properly (Offline Files/Folders). This depends on connectivity information and Network Connect/Disconnect and Logon/Logoff notifications from SENS.
- [COM+ Event System](/article/winnt-services-eventsystem.html) will try to notify the SENS of events, but will fail.

##### Recommended State:

- Automatic.

##### Default State:

- Automatic

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (SENS)

##### Supports:

- [Background Intelligent Transfer Service](/article/winnt-services-bits.html) (Win2k SP3+ only)
- [COM+ System Application](/article/winnt-services-comsysapp.html) (Vista+)

##### Depends:

- [COM+ Event System](/article/winnt-services-eventsystem.html)