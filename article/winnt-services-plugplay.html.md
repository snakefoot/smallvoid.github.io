---
title: 'Plug and Play'
date: '2000-06-06T16:08:09+02:00'
status: publish
permalink: /article/winnt-services-plugplay.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Plug and Play service.'
type: post
id: 572
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - plug-and-play
post_format: []
tags:
    - plug-and-play
---
##### Description:

 Enables automatic detection, installation and activation of new PnP devices attached to the computer.  
  
 Note if this service is not running properly, then the Device Manager will be empty with no items listed:
- Make sure the service is set to Automatic. More Info [MS KB311504](http://support.microsoft.com/kb/311504 "No Items Appear in the Device Manager List When You Open It [Q311504]")
- Make sure that SYSTEM has Full Control over the following registry key (Use Regedt32.exe):
  > \[HKEY\_LOCAL\_MACHINE /SYSTEM /CurrenControlSet /Enum\]
- Make sure that service is not hampered by malware/spyware/virus like [Apropos.C](http://securityresponse.symantec.com/avcenter/venc/data/spyware.apropos.c.html)
 
 Note in WinNT4 this service only provided some [wannabe PnP](/article/winnt4-plug-and-play.html), which mostly works when installing dialup modems.  
  
##### Recommended State:

- Win8: Manual
- Win7\\Vista\\WinXP\\Win2k\\WinNT4: Automatic

##### Default State:

- Win8: Manual
- Win7\\Vista\\WinXP\\Win2k\\WinNT4: Automatic

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k DcomLaunch](/article/winnt-services-wrapper.html) (PlugPlay)
- WinXP/Win2k3/Win2k/WinNT4: [services.exe](/article/winnt-services-wrapper.html) (PlugPlay)

##### Supports:

- [FAX Service](/article/winnt-services-fax.html) (Win7\\Vista\\WinXP\\Win2k\\WinNT4 only)
- [Telephony](/article/winnt-services-tapisrv.html) (Win7\\Vista\\WinXP\\Win2k\\WinNT4 only)
- [Remote Access Connection Manager](/article/winnt-services-rasman.html) (Win7\\Vista\\WinXP\\Win2k only)
- [Smart Card](/article/winnt-services-scardsvr.html) (Win7\\Vista\\WinXP\\Win2k only)
- [Virtual Disk Service](/article/winnt-services-vds.html) (Win7\\Vista\\Win2k3 only)
- [Windows Audio](/article/winnt-services-audiosrv.html) (Win7\\Vista\\WinXP only)
- [Windows Audio Endpoint Builder](/article/winnt-services-audioendpointbuilder.html) (Win7\\Vista only)
- [Tablet PC Input Service](/article/winnt-services-tabletinputservice.html) (Win7\\Vista only)
- [Windows Driver Foundation - User-mode Driver Framework](/article/winnt-services-wudfsvc.html) (Win7\\Vista only)
- [WWAN AutoConfig](/article/winnt-services-wwansvc.html) (Win7 only)
- [Windows Modules Installer](/article/winnt-services-trustedinstaller.html) (Vista only)
- [Logical Disk Manager](/article/winnt-services-dmserver.html) (Win2k/WinXP/Win2k3 only)
- [Logical Disk Manager Administrative](/article/winnt-services-dmadmin.html) (Win2k/WinXP/Win2k3 only)
- [Messenger](/article/winnt-services-messenger.html) (WinXP/Win2k3 only)
- [Windows Image Acquisition](/article/winnt-services-stisvc.html) (Win2k3 only)

##### Depends:

- None