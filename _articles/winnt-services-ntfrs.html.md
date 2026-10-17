---
title: 'Directory Replicator / File Replication Service'
date: '2000-06-06T01:02:18+02:00'
permalink: /article/winnt-services-ntfrs.html
author: Snakefoot
excerpt: 'Description and recommended settings for the File Replication service.'
type: post
id: 536
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
tags:
    - distributed-file-system
    - file-synchronization
---
##### Description:

 Directory Replicator or File Replication Service (FRS) provides control replication / synchronization of directories and files among multiple servers. It is used by the [Distributed File System (DFS)](/article/winnt-services-dfs.html) to automatically synchronize file catalogs. It is used by the Active Directory to automatically synchronize Domain Controllers.  
  
 More Info <a href="https://www.bing.com/search?q=KB+221111+Q221111" rel="nofollow" title="Description of FRS Entries in the Registry [Q221111]">MS KB221111</a>  
 More Info <a href="https://www.bing.com/search?q=KB+264822+Q264822" rel="nofollow" title="File Replication Service Stops Responding When Staging Area is Full [Q264822]">MS KB264822</a>  
 More Info <a href="https://www.bing.com/search?q=KB+272279+Q272279" rel="nofollow" title="How to Troubleshoot the File Replication Service and the Distributed File System (MS KB272279) [Q272279]">MS KB272279</a>  
 More Info <a href="https://www.bing.com/search?q=KB+272567+Q272567" rel="nofollow" title="File Replication Service Improvements in Windows 2000 Service Pack 2 [Q272567]">MS KB272567</a>  
 More Info <a href="https://www.bing.com/search?q=KB+308406+Q308406" rel="nofollow" title="FRS Event Log Error Codes [Q308406]">MS KB308406</a>  
  
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