---
title: 'Configure commit write for files on network shares'
date: '2005-06-23T22:56:08+02:00'
status: publish
permalink: /article/winnt-network-file-commit.html
author: Snakefoot
excerpt: 'Network file server can ignore client file flush requests and thus increase the network file performance.'
type: post
id: 449
category:
    - 'File Sharing'
    - 'File Sharing'
tag:
    - file-cache
    - file-system
    - network-performance
    - network-share
post_format: []
tags:
    - 'file-cache,file-system,network-share,network-performance'
---
When writing to a file it is possible to perform a commit operation, which specifies that all data in cache should be flushed to disc. If the machine crashes without having performed a commit operation, then all data in cache is lost. Therefore many applications often perform commit operations to avoid data loss, at the cost of disc performance.  
  
 When the file is placed on a network drive, then the flush request is converted to a SMB\_COM\_FLUSH message sent to the server, which causes the server to flush its cache and only when it is done, then it responds back to the client. Instead of just affecting the client machine, then it also affects the server, which can cause very slow performance for all clients using the server.  
  
 It is possible to configure the server so it will not perform the commit operation, and thus avoiding the slow file operation (The client will have flushed its own cache):

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  TreatHostAsStableStorage = 1 (Default = 0)  
>   
>  Note this should only be considered if the server is equipped with a redundant disc system along with battery backup.  
>   
>  More Info [MS KB840390](http://support.microsoft.com/kb/840390 "Software update to change the behavior of the SMB_COM_FLUSH command in Windows Server 2003 [Q840390]")  
>  More Info [MS KB894372](http://support.microsoft.com/kb/894372 "Support for Windows Server 2003 SP1 on Windows Storage Server 2003-based server appliances [Q894372]")

 Related [Configure hard disk cache to ignore flush requests](/article/hard-disk-cache.html)  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)