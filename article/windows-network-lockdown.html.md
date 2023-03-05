---
title: 'Lock down the network connection'
date: '2001-01-01T13:49:06+01:00'
status: publish
permalink: /article/windows-network-lockdown.html
author: Snakefoot
excerpt: 'There are several security issues one should take care of when having a network connection.'
type: post
id: 308
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - network-security
post_format: []
tags:
    - network-security
---
Depending on the version of Windows then different protocols and services are installed by default when the computer has a network adapter or a dialup modem. One seldom need other protcols than the TCPIP protocol, and should uninstall other network protocols like IPX and NetBEUI, as they generate a lot of broadcasting noise on the network, which hurts the network performance.  
  
 The Microsoft Network services allows one to share resources like files and printers, and access files and printers on other computers on the network. One should by careful about how to bind these services to the different network connections installed.

- **Client for Microsoft Networks** - Enables access to shared files and printers on Microsoft Networks. This service should only be installed for network connections which requires such access (Ex. dialup modems doesn't need this service).
- **File and Printer Sharing for Microsoft Networks** - Enables sharing of files and printers on Microsoft Network. Again this should only be installed for network connections where this is wanted, to avoid sharing personal files with all the people on the Internet (Ex. dialup modems doesn't need this service).
 
 To configure the binding of a network connection to these services:
- Win9x - Open Network Properties and change the properties for the TCP/IP protocol, and on the "Bindings"-fan uncheck the binding to file sharing.
- Win2k - Open "Network and Dial-up Connections" and in the menu select "Advanced" -&gt; "Advanced Settings".
 
 If having network connections that requires access to Microsoft Networks, then one should decide who should have access to files shared on the Microsoft Network:
- [How to enable Win9x filesharing in Windows 2000](/article/win2k-win9x-filesharing.html)
- [How to enable Win9x filesharing in Windows XP](/article/winxp-win9x-filesharing.html)
 
 If using Windows NT versions like Windows NT4, 2000, XP, 2003, then one should be make sure to lock down access to the user accounts, so people cannot logon to the machine from the network and allowing them access to the entire machine. More Info [Securing the local Administrator account](/article/winnt-secure-admin.html).  
  
 If the network connection is used to access the Internet, then it should one should strongly consider getting a firewall. Especially if not hidding behind a NAT router, which gives some protection from direct port attacks from the Internet, and if the same network connection is bound to the Microsoft Networks services for use on the Local Area Network (LAN).  
  
 Related [Creating a Local Area Network (LAN)](/article/troubleshooting-network.html)  
 Related [Limit protocols negotiations during dialup handshake](/article/win9x-dialup-handshake.html)  