---
title: 'Windows Driver Foundation - User-mode Driver Framework'
date: '2007-07-17T02:17:23+02:00'
status: publish
permalink: /article/winnt-services-wudfsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Driver Foundation - User-mode Driver Framework service.'
type: post
id: 716
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Manages user-mode driver host processes.  
  
 The Windows Driver Foundation (WDF) user-mode driver framework (UMDF) makes it possible to make device drivers that resides in user space. This has several advantages compared to running in kernel space:
- Increased stability as errors in a user space driver will not corrupt the kernel system address space and the structures that resides there.
- Increased security as a user space driver doesn't have direct access to all the kernel space functionality.
- Easier development as one can use C++ / User-mode-debugging / Win32 API.
 
 Each UMDF driver runs in a separate driver host process (WUDFHost.exe), which are managed by this service.  
  
 More Info [MS WDHC - User-Mode Driver Framework](http://www.microsoft.com/whdc/driver/wdf/UMDF_Intro.mspx "Introduction to the WDF User-Mode Driver Framework")
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (wudfsvc)

##### Supports:

- [Windows Biometric Service](/article/winnt-services-wbiosrvc.html) (Win7+)

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)