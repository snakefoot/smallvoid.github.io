---
title: Server
date: '2000-06-06T18:27:43+02:00'
status: publish
permalink: /article/winnt-services-lanmanserver.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Server service.'
type: post
id: 593
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - microsoft-network
post_format: []
tags:
    - microsoft-network
---
##### Description:

 The Server service provides Server Message Block (SMB) service, which enables sharing of your local resources to the network (such as printer and files). It also enables named pipe communication between applications running on other computers and your computer, which is used for RPC.  
  
 Stopping this service results in: - Disables sharing of files and printers on your computer with other computers on the network.
- Disables the computer from handling RPC requests.
- Disables named pipes communication with other machines.
- IIS User Manager will not be able to get access to the machine.
 
 Note one can use the NET command line tool to configure the server and set the computer comment or make it hidden:
 > Net Config Server /?

 Note when service is disabled or uninstalled, then the [IPC$ share](/article/winnt-ipc-share.html) will disappear and the command "NET SHARE" will give the following error message (Because the service is no longer available):
 > *The service name is invalid.  
 >   
 >  More help is available by typing NET HELPMSG 2185*

 Related [Optimizing the file sharing network to handle more traffic](/article/winnt-smb-settings.html)  
 Related [Graweg NetApi32.dll Exploit](/article/winnt-graweg-netapi32-exploit.html)  
  
 More Info [MS KB314498](http://support.microsoft.com/kb/314498 "Server Service Configuration and Tuning [Q314498]")  
  
##### Recommended State:

- Automatic, if wanting to share files and printers.
- Disabled, if no files to share. Uninstall the network component "File and Printer Sharing for Microsoft Networks" to disable.

##### Default State:

- Automatic

##### Process Name:

- Win8/Win7/Vista/WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (lanmanserver)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (lanmanserver)

##### Supports:

- [Computer Browser](/article/winnt-services-browser.html)
- [HomeGroup Listener](/article/winnt-services-homegrouplistener.html) (Win7 only)
- [Distributed File System](/article/winnt-services-dfs.html) (Win2k/Win2k3 only)

##### Depends:

- [Security Account Manager](/article/winnt-services-samss.html) (Vista+)