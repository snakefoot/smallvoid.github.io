---
title: 'Configure the memory usage of the Server service'
date: '2000-01-01T22:04:31+01:00'
status: publish
permalink: /article/winnt-server-config.html
author: Snakefoot
excerpt: 'Adjust the memory usage of the server service according to the server role.'
type: post
id: 370
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-performance
post_format: []
tags:
    - 'network-performance,microsoft-network'
---
The <a href="">Server Service</a> enables the the computer to act as a file and printer sharing server. Windows server edition will by default configure it self to maximize memory usage for the Server service to act like network file server. If server role is only to act as file server for 10 users or less, then one should consider trimming down the memory usage of the server service.  
  
 To change the configuration of the server service:

- **WinNT4** - Go to Control Panel -&gt; Network -&gt; Services, and choose "Properties" for "Server".
- **Win2k/Win2k3:**
  1. Open Control Panel and double click Network and Dial-up Connections
  2. Right-click the "Local Area Connection" and select properties
  3. Select "File and Printer Sharing for Microsoft Networks" and press properties
 
 The different configurations to choose between:
- Minimize Memory Used
- Balance
- Maximize Throughput for File Sharing (Will also enable [LargeSystemCache](/article/winnt-system-cache.html))
- Maximize Throughput for Network Applications
 
 The change of configuration will be reflected in this registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\lanmanserver \\parameters\]  
>  size = 1 (1 = Minimize, 2 = Balance, 3 = Maximize)

 Related [Optimizing the file sharing network to handle more traffic](/article/winnt-smb-settings.html)