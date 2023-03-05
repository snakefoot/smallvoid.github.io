---
title: 'Directory Replicator / File Replication Service'
date: '2000-06-06T01:02:18+02:00'
status: publish
permalink: /article/winnt-services-ntfrs.html
author: Snakefoot
excerpt: 'Description and recommended settings for the File Replication service.'
type: post
id: 536
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - distributed-file-system
    - file-synchronization
post_format: []
tags:
    - 'distributed-file-system,file-synchronization'
---
##### Description:

 Directory Replicator or File Replication Service (FRS) provides control replication / synchronization of directories and files among multiple servers. It is used by the [Distributed File System (DFS)](/article/winnt-services-dfs.html) to automatically synchronize file catalogs. It is used by the Active Directory to automatically synchronize Domain Controllers.  
  
 More Info [MS KB221111](http://support.microsoft.com/kb/221111 "Description of FRS Entries in the Registry [Q221111]")  
 More Info [MS KB264822](http://support.microsoft.com/kb/264822 "File Replication Service Stops Responding When Staging Area is Full [Q264822]")  
 More Info [MS KB272279](http://support.microsoft.com/kb/272279 "How to Troubleshoot the File Replication Service and the Distributed File System (MS KB272279) [Q272279]")  
 More Info [MS KB272567](http://support.microsoft.com/kb/272567 "File Replication Service Improvements in Windows 2000 Service Pack 2 [Q272567]")  
 More Info [MS KB308406](http://support.microsoft.com/kb/308406 "FRS Event Log Error Codes [Q308406]")  
  
##### Recommended State:

- Manual

##### Default State:

- Manual

##### Process Name:

- ntfrs.exe (ntfrs)

##### Supports:

- None

##### Depends:

- [Event Log](/article/winnt-services-eventlog.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Distributed File System](/article/winnt-services-dfs.html) (Unofficial)
- [COM+ Event System](/article/winnt-services-eventsystem.html) (Win2k3 only)