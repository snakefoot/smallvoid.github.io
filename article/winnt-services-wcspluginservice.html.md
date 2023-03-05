---
title: 'Windows Color System'
date: '2007-07-17T02:17:09+02:00'
status: publish
permalink: /article/winnt-services-wcspluginservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Color System service.'
type: post
id: 713
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The WcsPlugInService service hosts third-party Windows Color System color device model and gamut map model plug-in modules. These plug-in modules are vendor-specific extensions to the Windows Color System baseline color device and gamut map models. Stopping or disabling the WcsPlugInService service will disable this extensibility feature, and the Windows Color System will use its baseline model processing rather than the vendor's desired processing. This might result in inaccurate color rendering.  
  
 Supports image input and display outputs from different vendors to be calibrated, so they deliver a uniform image display.  
  
 More Info [Wiki: Windows Color System](http://en.wikipedia.org/wiki/Windows_Color_System).
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k wcssvc](/article/winnt-services-wrapper.html) (WcsPlugInService)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)