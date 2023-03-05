---
title: Alerter
date: '2000-06-06T01:00:00+02:00'
status: publish
permalink: /article/winnt-services-alerter.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Alerter service.'
type: post
id: 520
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Makes it possible to automatically sent messages to registered users, about certain system events or alerts when they happen. The registered users needs to have the [Messenger service](/article/winnt-services-messenger.html) started to receive the messages.  
  
 More Info [MS KB243625](http://support.microsoft.com/kb/243625 "How to Configure Administrative Alerts in Windows 2000 [Q243625]")  
  
##### Recommended state:

- Disabled : if you don't need to alert users about system events over the network.

##### Default State:

- Win2k Srv.: Automatic
- Win2k Pro.: Manual
- WinXP: Manual
- WinXP SP2: Disabled
- Win2k3: Disabled

##### Proces name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Alerter)
- WinXP/2k3: [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (Alerter)

##### Supports:

- None

##### Depends:

- [Workstation](/article/winnt-services-lanmanworkstation.html)