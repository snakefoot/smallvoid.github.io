---
title: 'Windows Remote Management (WS-Management)'
date: '2007-07-17T02:18:21+02:00'
status: publish
permalink: /article/winnt-services-winrm.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Remote Management (WS-Management) service.'
type: post
id: 727
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Windows Remote Management (WinRM) service implements the WS-Management protocol for remote management. WS-Management is a standard web services protocol used for remote software and hardware management. The WinRM service listens on the network for WS-Management requests and processes them. The WinRM Service needs to be configured with a listener using winrm.cmd command line tool or through Group Policy in order for it to listen over the network. The WinRM service provides access to WMI data and enables event collection. Event collection and subscription to events require that the service is running. WinRM messages use HTTP and HTTPS as transports. The WinRM service does not depend on IIS but is preconfigured to share a port with IIS on the same machine. The WinRM service reserves the /wsman URL prefix. To prevent conflicts with IIS, administrators should ensure that any websites hosted on IIS do not use the /wsman URL prefix.  
  
 Makes it possible for remote computers to make WMI queries. Listens for WS-Management requests on port 80 and 443, which it shares with IIS using the /wsman URL prefix. More Info [MSDN - Windows Remote Management](http://msdn2.microsoft.com/en-us/library/aa384426.aspx).
 
##### Recommended state:

- Disabled for security reasons

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (WinRM)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)