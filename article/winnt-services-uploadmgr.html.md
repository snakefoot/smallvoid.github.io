---
title: 'Upload Manager'
date: '2003-06-05T20:13:30+02:00'
status: publish
permalink: /article/winnt-services-uploadmgr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Upload Manager service.'
type: post
id: 611
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Microsoft's own protocol for transferring files between your computer and Microsoft. It is mainly used to upload the hardware profile for your computer to Microsoft, and download details of what drivers to use.  
- [Driver Protection](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws03mngd/06_s3dri.mspx "Using Windows Server 2003 in a Managed Environment - Driver Protection") - Uses this service to get updated [lists](http://www.microsoft.com/whdc/archive/drv_protect.mspx "Driver Protection List for Windows XP and Windows Server 2003") from Microsoft about what drivers are bad and should not be activated.
- [Online Device Help](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws03mngd/16_s3onl.mspx "Windows Server 2003 in a Managed Environment - Online Device Help") - Uses this service to get details from Microsoft of what drivers to use for unknown devices.
 
 If the service is disabled then some of the online help will stop working.  
  
##### Recommended State:

- Disabled, if able to live without the online help.

##### Default State:

- WinXP: Automatic
- Win2k3: Disabled
- WinXP SP2+: Not installed

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (uploadmgr)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)