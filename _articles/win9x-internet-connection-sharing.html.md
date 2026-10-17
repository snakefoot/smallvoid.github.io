---
title: 'Setting up Internet Connection Sharing in Windows 98 SE / Me'
date: '2001-08-01T21:29:14+02:00'
permalink: /article/win9x-internet-connection-sharing.html
author: Snakefoot
excerpt: 'How to configure Internet Connection Sharing to configure a gateway to the Internet for other computers.'
type: post
id: 199
categories:
    - windows-98_network
    - windows-me_network
tags:
    - default-gateway
    - internet-connection-sharing
    - network-router
    - proxy
---
Microsoft have created several articles to share a single Internet Connection between several computers.

- <a href="https://www.bing.com/search?q=KB+234815+Q234815" rel="nofollow">Description of Internet Connection Sharing (MS KB234815)</a>
- <a href="https://www.bing.com/search?q=KB+230150+Q230150" rel="nofollow">How to Configure a Permanent IP Address for Network Devices (MS KB230150)</a>
- <a href="https://www.bing.com/search?q=KB+238135+Q238135" rel="nofollow">How to Troubleshoot Internet Connection Sharing Problems (MS KB238135)</a>
- <a href="https://www.bing.com/search?q=KB+265728+Q265728" rel="nofollow">Internet Connection Sharing Requires Two Network Adapters on the Host Computer (MS KB265728)</a>
- <a href="https://www.bing.com/search?q=KB+273587+Q273587" rel="nofollow">How to Configure ICS for Use with DSL Connections That Use PPPoE Adapters (MS KB273587)</a>
 
 Note if using ICS to share a broadband(high speed) connection(Cable or DSL) with other computers, then you might not get the performance you expected. This might be solved by deleting this registry key:  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\ICSharing \\Settings \\General\]  
> **InternetMTU** = ?  
>   
>  More info <a href="https://www.bing.com/search?q=KB+230116+Q230116" rel="nofollow" title="Slow Transfer Rates with ICS and High-Bandwidth Devices (MS KB230116) [Q230116]">MS KB230116</a>

 Note to setup a FTP- / Web- / Game-server while using Internet Connection Sharing, then one must create TCP/IP port forwards to the computer running the service. The utility [ICS Configuration](http://www.practicallynetworked.com/sharing/ics/icsconfiguration.htm) makes it easy to map ports to the right computer.  