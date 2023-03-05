---
title: 'Windows Image Acquisition (WIA)'
date: '2003-06-05T21:32:16+02:00'
status: publish
permalink: /article/winnt-services-stisvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Image Acquisition service.'
type: post
id: 617
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - TWAIN
post_format: []
tags:
    - TWAIN
---
##### Description:

 Provides image acquisition services for scanners &amp; cameras. It is used for transferring the pictures from a camera or scanner to the computer.  
  
 WIA is an attempt to make it easier for camera and scanner developers to write drivers, as it was rather difficult within [Twain.org](http://www.twain.org/). WIA has its own API for extracting pictures, but it also includes a TWAIN compatibility layer.  
  
 Note Windows Vista (and XP SP2) comes with WIA ver. 2.0 which brings new features, but also breaks compatibility with devices and drivers using WIA ver. 1.0. Vista now uses the Picture Transfer Protocol (PTP) which is part of the Windows Portable Devices (WPD) standard for transfering pictures instead of WIA. More Info [MS KB927836](http://support.microsoft.com/kb/927836 "A digital still camera is not recognized in Windows Vista or in Windows XP")  
  
 More Info [MS KB307001](http://support.microsoft.com/kb/307001 "HOW TO: Enable Logging of Wiadebug.log in Windows XP [Q307001]")  
 More Info [MS KB819017](http://support.microsoft.com/kb/819017 "Long Delay Before Files Appear in My Computer in Windows XP [Q819017]")  
 More Info [MS KB823612](http://support.microsoft.com/kb/823612 "Windows XP Takes a Long Time to Start [Q823612]")  
  
##### Recommended State:

- Manual, if using digital camera or scanners.
- Disabled, if not wanting the service to interfere in startup detection or when browsing My Computer.

##### Default State:

- WinXP: Manual.
- Win2k3: Disabled.
- Vista/Win7: Manual.

##### Process Name:

- [svchost.exe -k imgsvc](/article/winnt-services-wrapper.html) (stisvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Shell Hardware Detection](/article/winnt-services-shellhwdetection.html) (Vista+)