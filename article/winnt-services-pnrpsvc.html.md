---
title: 'Peer Name Resolution Protocol'
date: '2007-07-17T02:15:07+02:00'
status: publish
permalink: /article/winnt-services-pnrpsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Peer Name Resolution Protocol service.'
type: post
id: 688
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - netPeerTcpBinding
    - PNRP
post_format: []
tags:
    - 'PNRP,netPeerTcpBinding'
---
##### Description:

 Enables Serverless Peer Name Resolution over the Internet. If disabled, some Peer to Peer and Collaborative applications, such as [Windows Meeting Space](http://www.microsoft.com/windows/windows-vista/features/meeting-space.aspx), may not function.  
  
 Note on WinXP SP2/SP3 this service can be installed manually through Control Panel -&gt; Add or Remove Programs -&gt; Add/Remove Windows Components -&gt; "Networking Services"-button -&gt; "Peer to Peer"-checkbox.  
  
 More Info [Wiki: Peer Name Resolution Protocol](http://en.wikipedia.org/wiki/Peer_Name_Resolution_Protocol)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win8/Win7 - [svchost.exe -k LocalServicePeerNet](/article/winnt-services-wrapper.html) (PNRPSvc)
- Vista - [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (PNRPSvc)
- WinXP - [svchost.exe -k p2psvc](/article/winnt-services-wrapper.html) (PNRPSvc)

##### Supports:

- [Peer Networking Grouping](/article/winnt-services-p2psvc.html)
- [PNRP Machine Name Publication Service](/article/winnt-services-pnrpautoreg.html)

##### Depends:

- [Peer Networking Identity Manager](/article/winnt-services-p2pimsvc.html)