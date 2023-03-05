---
title: 'Offline Files'
date: '2007-07-17T02:14:57+02:00'
status: publish
permalink: /article/winnt-services-cscservice.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Offline Files service.'
type: post
id: 686
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - file-synchronization
    - offline-files
post_format: []
tags:
    - 'file-synchronization,offline-files'
---
##### Description:

 The Offline Files service performs maintenance activities on the Offline Files cache, responds to user logon and logoff events, implements the internals of the public API, and dispatches interesting events to those interested in Offline Files activities and changes in cache state.  
  
 The Offline Files cache is useful when using a laptop, which is not always connected to the file server. Select a file or folder in the Windows Explorer and in the right-click menu select **Always Available Offline** (Previously named "Make Available Offline") and it will be cached in the Client Side Caching (CSC) folder located here:
 > C:\\Windows\\CSC

 More Info [MS Technet: What's New in Offline Files for Windows Vista](http://technet2.microsoft.com/WindowsVista/en/library/bb819260-0fdc-4003-bc23-04beac2108bd1033.mspx)
 
##### Recommended state:

- Disabled if not synchronizing files between computers.

##### Default State:

- Win8: Automatic (Trigger Start)
- Win7/Vista: Automatic

##### Proces name:

- [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (CscService)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)