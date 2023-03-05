---
title: 'Distributed File System'
date: '2000-07-23T01:02:20+02:00'
status: publish
permalink: /article/winnt-services-dfs.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Distributed File System service.'
type: post
id: 537
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - distributed-file-system
post_format: []
tags:
    - distributed-file-system
---
##### Description:

 Distributed File System (DFS) manages logical volumes distributed across a local or wide area network. It maintains a large catalog of all the files with their physical location. The catalog is usually replicated on multiple machines and being synchronized using [File Replication Service](/article/winnt-services-ntfrs.html). The catalog enables clients to requests a file using a logical name, without needing to specify the exact machine that stores the actual file.  
  
 More Info [MS KB241452](http://support.microsoft.com/kb/241452 "How to Install Distributed File System (DFS) on Windows 2000 [Q241452]")  
 More Info [MS KB272702](http://support.microsoft.com/kb/272702 "Unable to Create DFS Replication Policy with Missing Administrative Shares [Q272702]")  
 More Info [MS KB812487](http://support.microsoft.com/kb/812487 "Overview of DFS in Windows 2000 [Q812487]")  
 More Info [MS KB824730](http://support.microsoft.com/kb/824730 "Link Target Servers in DFS Referral Responses Are Sometimes Sorted in Random Order [Q824730]")  
  
##### Recommended State:

- Disabled, if on a simple home network.

##### Default State:

- Win2k Srv.: Automatic
- Win2k3: Automatic

##### Process Name:

- Dfssvc.exe (DFS)

##### Supports:

- None

##### Depends:

- [Server](/article/winnt-services-lanmanserver.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)
- [Security Accounts Manager](/article/winnt-services-samss.html) (Win2k3 only)
- [File Replication](/article/winnt-services-ntfrs.html) (Unofficial)