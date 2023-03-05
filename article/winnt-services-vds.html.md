---
title: 'Virtual Disk Service (VDS)'
date: '2003-09-23T20:20:16+02:00'
status: publish
permalink: /article/winnt-services-vds.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Virtual Disk service.'
type: post
id: 613
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Virtual Disk Service (VDS) implements a single, uniform interface for managing disks. Each hardware vendor writes a VDS "provider" that translates the general purpose VDS APIs into specific instructions for their hardware (Targeted for Storage Area Network(SAN) ).  
 Microsoft has implemented VDS providers for basic and dynamic disks. This brings functionality to basic disks, such as online growth, that formerly only applied to dynamic disks.  
  
 More Info [MS KB828220](http://support.microsoft.com/kb/828220 "When You Convert BASIC Disks to Dynamic Disks, the Operation Takes a Long Time [Q828220]")  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- vds.exe (VDS)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Plug and Play](/article/winnt-services-plugplay.html)