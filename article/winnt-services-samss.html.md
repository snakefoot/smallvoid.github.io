---
title: 'Security Accounts Manager (SAM)'
date: '2000-06-06T16:45:58+02:00'
status: publish
permalink: /article/winnt-services-samss.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Security Accounts Manager service.'
type: post
id: 591
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - sam-database
post_format: []
tags:
    - sam-database
---
##### Description:

 Stores security information for local user accounts.  
  
 This service is responsible for making the connection to the SAM-database (Contains available user-accounts and groups). The SAM-database can either be placed in the local registry or in the Active Directory (If available). When the service has made the connection it announces to the system that the SAM-database is available, so other services can start accessing the SAM-database.  
  
##### Recommended State:

- Automatic.

##### Default State:

- Automatic

##### Process Name:

- [lsass.exe](/article/winnt-services-wrapper.html) (SamSs)

##### Supports:

- [Distributed Transaction Coordinator](/article/winnt-services-msdtc.html)
- [KtmRm for Distributed Transaction Coordinator](/article/winnt-services-ktmrm.html) (Vista+)
- [Server](/article/winnt-services-lanmanserver.html) (Vista+)
- [HTTP SSL](/article/winnt-services-httpfilter.html) (Win2k3 only)
- [Distributed File System](/article/winnt-services-dfs.html) (Win2k3 only)
- [Intersite Messaging](/article/winnt-services-ismserv.html) (Win2k/Win2k3 only)

##### Depends:

- None