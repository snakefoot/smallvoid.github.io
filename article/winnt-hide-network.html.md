---
title: 'Hide computer from the other computers on the network'
date: '2001-01-12T22:36:28+01:00'
status: publish
permalink: /article/winnt-hide-network.html
author: Snakefoot
excerpt: 'How to configure the computer not to announce itself on the Microsoft Network.'
type: post
id: 206
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - master-browser
    - microsoft-network
post_format: []
tags:
    - 'microsoft-network,master-browser'
---
Every 12 mins the [Server Service](/article/winnt-services-lanmanserver.html) will announce itself to the [Master Browser](/article/winnt-master-browser.html) on each protocol installed. If having a 1000 clients doing this on two protocols like the TCPIP- and Netbios-protocol, then it will lead to 10000 packets/hour.  
  
 One can stop this announcement / broadcasting by adding this DWORD value in the registry:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  Hidden = 1

 One can also configure the machine not to show on the network using command line:
 > net config server /hidden:yes

 Note it may take up to half an hour before being removed from the browser list and become invisible in the Network Neighborhood/My Network Places.  
  
 Related [Make your network shares hidden](/article/hidden-file-shares.html)  
  
 More Info [MS KB265284](http://support.microsoft.com/kb/265284 "How to Hide the Server's Computer Name from Other Computers in the Domain [Q265284]")  
 More Info [MS KB314498](http://support.microsoft.com/kb/314498 "Server Service Configuration and Tuning [Q314498]")  