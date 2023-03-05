---
title: 'Distributed Link Tracking Client'
date: '2000-07-23T01:08:03+02:00'
status: publish
permalink: /article/winnt-services-trkwks.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Distributed Link Tracking Client service.'
type: post
id: 538
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - link-shortcut
    - link-tracking
post_format: []
tags:
    - 'link-shortcut,link-tracking'
---
##### Description:

 Maintains shortcuts/links to NTFS files within a computer or across computers in a network. It ensures that links are updated when:
- The link source file is renamed.
- The link source file is moved to another folder on the same volume or a different volume of the same computer.
- The link source file is moved to another computer in the network.
- The shared network folder containing the link source file is renamed.
 
 The following scenarios can also be handled if in a domain where the [Distributed Link Tracking Server](/article/winnt-services-trksrv.html) is running:
- The link source file is moved between computers
- The computer containing the link source file is renamed.
- The volume containing the link source file is moved to another computer within the same domain.
 
 It performs these services by monitoring activity on the NTFS volumes and store maintenance information in a file called Tracking.log, which is placed in the root folder "System Volume Information".  
  
##### Recommended State:

- Disabled, if on a simple home network.
- Automatic, if connected to a domain and uses a NTFS file system.

##### Default State:

- Automatic

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k LocalSystemNetworkRestricted](/article/winnt-services-wrapper.html) (TrkWks)
- WinXP Pro/2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (TrkWks)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (TrkWks)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)