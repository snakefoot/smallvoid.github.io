---
title: 'License Logging Service'
date: '2000-06-06T13:49:44+02:00'
status: publish
permalink: /article/winnt-services-licenseservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the License Logging service.'
type: post
id: 558
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 License Logging Service provides license tracking on a server or Domain Controller (DC).  
  
 It will post a warning in the Application Event Log with Event ID 221, if there are more users accessing the machine than there are licenses.  
  
 The licenses can be configured on the server by opening the **Control Panel** and double clicking the **Licensing**-applet.  
  
 Note if running an Exchange Server this service will conflict with the SBS License control, and will block out users even though enough Exchange Server Licenses. Disable this service to avoid the conflict or install the patch [MS KB305138](http://support.microsoft.com/kb/305138 ""Out of License" Error Messages in SBS 2000 Event Logs [Q305138]").  
  
 More Info [MS KB153140](http://support.microsoft.com/kb/153140 "How to Reset License Manager Information [Q153140]")  
 More Info [MS KB185953](http://support.microsoft.com/kb/185953 "How License Service Keeps Track of License Usage [Q185953]")  
 More Info [MS KB193218](http://support.microsoft.com/kb/193218 "Configuring License Service Replication in Windows NT Server 4.0 or Windows 2000 [Q193218]")  
 More Info [MS KB273475](http://support.microsoft.com/kb/273475 "Licensing in Windows 2000 and Differences with Windows NT 4.0 [Q273475]")  
 More Info [MS KB824196](http://support.microsoft.com/kb/824196 "Description of the License Logging Service in Windows Server Operating Systems [Q824196]")  
  
##### Recommended State:

- Disabled, if on a simple home network.
- Automatic, if you for some reason has a MS License for your installation.

##### Default State:

- Win2k Srv.: Automatic.
- Win2k3: Disabled.

##### Process Name:

- llssrv.exe (LicenseService)

##### Supports:

- None

##### Depends:

- None