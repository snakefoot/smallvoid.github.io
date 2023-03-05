---
title: 'Net.Tcp Port Sharing Service'
date: '2007-07-17T02:14:37+02:00'
status: publish
permalink: /article/winnt-services-nettcpportsharing.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Net.Tcp Port Sharing Service.'
type: post
id: 682
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - WCF
post_format: []
tags:
    - WCF
---
##### Description:

 Provides ability to share TCP ports over the net.tcp protocol.  
  
 Supports the Windows Communication Foundation (WCF) in .NET, and makes it possible for several applications to use the same TCP port number for network communication (Like IIS HTTP.SYS allows multiple applications to use port 80). More Info [MSDN - Net.TCP Port Sharing](http://msdn2.microsoft.com/en-us/library/ms734772.aspx).
 
##### Recommended state:

- Disabled

##### Default State:

- Disabled

##### Proces name:

- SMSvcHost.exe (NetTcpPortSharing)

##### Supports:

- none

##### Depends:

- none