---
title: 'Shell Hardware Detection'
date: '2003-06-05T18:43:09+02:00'
status: publish
permalink: /article/winnt-services-shellhwdetection.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Shell Hardware Detection service.'
type: post
id: 595
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - autoplay
post_format: []
tags:
    - autoplay
---
##### Description:

 Supports Autoplay which is launched when inserting a USB storage device, CD or other removable storage (Like scanner or camera), and gives you the option to select what application to use with the device. Autoplay is an extension of [AutoRun](/article/winnt-autorun.html).  
  
 Some experiences that Windows takes a long time to boot when this service is set to Automatic.  
  
 If the service is disabled then the AutoPlay-Tab will not be shown when viewing properties for an AutoPlay device like CD-ROM/DVD.  
  
##### Recommended State:

- Disabled if able to live without the Autoplay wizard.

##### Default State:

- Automatic.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (ShellHWDetection)

##### Supports:

- [Windows Image Acquisition](/article/winnt-services-stisvc.html) (Win7/Vista/WinXP/Win2k3 only)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)