---
title: 'PnP-X IP Bus Enumerator'
date: '2007-07-17T02:15:26+02:00'
status: publish
permalink: /article/winnt-services-ipbusenum.html
author: Snakefoot
excerpt: 'Description and recommended settings for the PnP-X IP Bus Enumerator service.'
type: post
id: 692
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Plug and Play Extensions (PnP-X) bus enumerator service manages the virtual network bus. It discovers network connected devices using the [SSDP](/article/winnt-services-ssdpsrv.html)/WS discovery protocols and gives them presence in PnP. If this service is stopped or disabled, presence of NCD devices will not be maintained in PnP. All pnpx based scenarios will stop functioning.  
  
 Allows Network Connected Devices (NCD) to appear like a physically attached device in the Windows Plug-and-Play (PnP) subsystem.  
  
 More Info [MSDN - Web Services on Devices](http://msdn.microsoft.com/en-us/library/bb756908.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (IPBusEnum)

##### Supports:

- [Windows Media Center Extender Service](/article/winnt-services-mcx2svc.html)

##### Depends:

- [Function Discovery Provider Host](/article/winnt-services-fdphost.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)