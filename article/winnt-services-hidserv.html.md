---
title: 'Human Interface Device Access / HID Input Service'
date: '2003-06-05T02:09:22+02:00'
status: publish
permalink: /article/winnt-services-hidserv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Human Interface Device Access service.'
type: post
id: 550
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - keyboard
    - mouse
    - usb
post_format: []
tags:
    - 'keyboard,mouse,USB'
---
##### Description:

 Provides a generic interface to Human Interface Devices (HID) like keyboard, mouse and joystick for accessing, configuring and maintaining hotkeys.  
  
 This service can become important if fx. having a keyboard with extra buttons/hotkeys for controlling sound volume, or if using USB Speakers.  
  
 Note the service will be installed automatically if it detects a device which needs the service, but some times it fails. If getting the error below when starting the service, then one have to open the archive **&lt;install-cd&gt;\\i368\\Drivers.cab** and extract the following files to **%SystemRoot%\\System32**: - **hidserv.dll**
- **mouhid.sys**
- **mouclass.sys**

> *Event ID: 7023  
>   
>  Could not start the Human Interface Device Access service on Local Computer.  
>  Error 126: the specified module could not be found.*

##### Recommended State:

- Disabled, if not using keyboards/mouse/joysticks extended with extra buttons that need mapping.
- Manual, if having many buttons to push.

##### Default State:

- Win8: Manual (Trigger Start - DEVICE INTERFACE ARRIVAL)
- Win7: Manual
- Vista: Automatic
- Win2k: Automatic
- WinXP: Manual
- WinXP SP1/Win2k3: Disabled

##### Process Name:

- Win2k: hidserv.exe (HidServ)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (HidServ)
- Vista/Win7: [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (HidServ)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (WinXP/Win2k3 only)