---
title: 'License Logging Service'
date: '2000-06-06T13:49:44+02:00'
permalink: /article/winnt-services-licenseservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the License Logging service.'
type: post
id: 558
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
tags: []
---
##### Description:

 License Logging Service provides license tracking on a server or Domain Controller (DC).  
  
 It will post a warning in the Application Event Log with Event ID 221, if there are more users accessing the machine than there are licenses.  
  
 The licenses can be configured on the server by opening the **Control Panel** and double clicking the **Licensing**-applet.  
  
 Note if running an Exchange Server this service will conflict with the SBS License control, and will block out users even though enough Exchange Server Licenses. Disable this service to avoid the conflict or install the patch <a href="https://www.bing.com/search?q=KB%20305138%20Q305138" rel="nofollow" title="'Out of License' Error Messages in SBS 2000 Event Logs [Q305138]">MS KB305138</a>.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20153140%20Q153140" rel="nofollow" title="How to Reset License Manager Information [Q153140]">MS KB153140</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20185953%20Q185953" rel="nofollow" title="How License Service Keeps Track of License Usage [Q185953]">MS KB185953</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20193218%20Q193218" rel="nofollow" title="Configuring License Service Replication in Windows NT Server 4.0 or Windows 2000 [Q193218]">MS KB193218</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20273475%20Q273475" rel="nofollow" title="Licensing in Windows 2000 and Differences with Windows NT 4.0 [Q273475]">MS KB273475</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20824196%20Q824196" rel="nofollow" title="Description of the License Logging Service in Windows Server Operating Systems [Q824196]">MS KB824196</a>  
  
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