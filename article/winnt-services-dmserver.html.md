---
title: 'Logical Disk Manager'
date: '2000-07-23T14:04:02+02:00'
status: publish
permalink: /article/winnt-services-dmserver.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Logical Disk Manager service.'
type: post
id: 559
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dynamic-disks
    - ntfs
post_format: []
tags:
    - 'dynamic-disks,ntfs'
---
##### Description:

 Logical Disk Manager Watchdog Service that detects the appearance/disappearance of hard drives and the partitions they contains.  
  
 Note if this service is stopped, then dynamic disk status and configuration information might become outdated. Therefore if one is considering to change this service state to Manual, then make sure that none of the disks in the system are configured as dynamic disks.  
  
 More Info [MS KB314343](http://support.microsoft.com/kb/314343 "Basic Storage Versus Dynamic Storage in Windows XP [Q314343]")  
 More Info [MS KB329707](http://support.microsoft.com/kb/329707 "Best Practices for Using Dynamic Disks on Windows 2000-Based Computers [Q329707]")  
  
##### Recommended State:

- Automatic.

##### Default State:

- Win2k: Automatic.
- WinXP Home: Manual.
- WinXP Pro: Automatic.
- Win2k3: Automatic.

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (dmserver)
- WinXP/2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (dmserver, System User)

##### Supports:

- [Logical Disk Manager Administrative Service](/article/winnt-services-dmadmin.html) (WinXP only)

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html) (WinXP only)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html) (WinXP only)