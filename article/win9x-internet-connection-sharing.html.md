---
title: 'Setting up Internet Connection Sharing in Windows 98 SE / Me'
date: '2001-08-01T21:29:14+02:00'
status: publish
permalink: /article/win9x-internet-connection-sharing.html
author: Snakefoot
excerpt: 'How to configure Internet Connection Sharing to configure a gateway to the Internet for other computers.'
type: post
id: 199
category:
    - Network
    - Network
tag:
    - default-gateway
    - internet-connection-sharing
    - network-router
    - proxy
post_format: []
tags:
    - 'internet-connection-sharing,default-gateway,proxy,network-router'
---
Microsoft have created several articles to share a single Internet Connection between several computers.

- [Description of Internet Connection Sharing (MS KB234815)](http://support.microsoft.com/kb/234815)
- [How to Configure a Permanent IP Address for Network Devices (MS KB230150)](http://support.microsoft.com/kb/230150)
- [How to Troubleshoot Internet Connection Sharing Problems (MS KB238135)](http://support.microsoft.com/kb/238135)
- [Internet Connection Sharing Requires Two Network Adapters on the Host Computer (MS KB265728)](http://support.microsoft.com/kb/265728)
- [How to Configure ICS for Use with DSL Connections That Use PPPoE Adapters (MS KB273587)](http://support.microsoft.com/kb/273587)
 
 Note if using ICS to share a broadband(high speed) connection(Cable or DSL) with other computers, then you might not get the performance you expected. This might be solved by deleting this registry key:  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\ICSharing \\Settings \\General\]  
> **InternetMTU** = ?  
>   
>  More info [MS KB230116](http://support.microsoft.com/kb/230116 "Slow Transfer Rates with ICS and High-Bandwidth Devices (MS KB230116) [Q230116]")

 Note to setup a FTP- / Web- / Game-server while using Internet Connection Sharing, then one must create TCP/IP port forwards to the computer running the service. The utility [ICS Configuration](http://www.practicallynetworked.com/sharing/ics/icsconfiguration.htm) makes it easy to map ports to the right computer.  