---
title: 'Netmeeting Remote Desktop Sharing'
date: '2003-06-05T15:25:12+02:00'
status: publish
permalink: /article/winnt-services-mnmsrvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Netmeeting Remote Desktop Sharing service.'
type: post
id: 564
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - netmeeting
    - remote-desktop
post_format: []
tags:
    - 'netmeeting,remote-desktop'
---
##### Description:

 Allows authorized people to remotely access your Windows desktop using NetMeeting.  
  
 Related [Uninstall/Reinstall Netmeeting in Windows XP/2000](/article/winnt-install-netmeeting.html)  
  
##### Recommended State:

- Disabled, for security and if not using netmeeting.
- Manual, if using this feature of netmeeting.

##### Default State:

- Win2k/WinXp: Manual.
- Win2k3: Disabled.

##### Process Name:

- mnmsrvc.exe (mnmsrvc)

##### Supports:

- None

##### Depends:

- None