---
title: 'Tablet PC Input Service'
date: '2007-07-17T02:16:24+02:00'
status: publish
permalink: /article/winnt-services-tabletinputservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Tablet PC Input Service.'
type: post
id: 704
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Enables Tablet PC pen and ink functionality.  
  
 The [Snipping Tool](http://windowshelp.microsoft.com/Windows/en-US/Help/1337cdba-52a2-4704-ad4d-2d7bace605b41033.mspx "Use Snipping Tool to capture screen shots") uses this service to turn the screen into an "inkable" surface, where one can write comments or draw and finally save the custom screenshot as an image.
 
##### Recommended state:

- Disabled unless using the Snipping Tool

##### Default State:

- Win7 - Manual
- Vista - Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (TabletInputService)

##### Supports:

- none

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)