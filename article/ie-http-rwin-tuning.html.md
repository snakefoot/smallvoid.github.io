---
title: 'Enable auto-tuning of RWIN in Internet Explorer on Vista'
date: '2008-10-02T02:42:48+02:00'
status: publish
permalink: /article/ie-http-rwin-tuning.html
author: Snakefoot
excerpt: 'Configure TCPIP receive window auto-tuning for HTTP connections for faster download.'
type: post
id: 772
category:
    - 'Internet Explorer (IE7)'
    - Network
tag:
    - network-performance
    - rwin
    - tcpip
post_format: []
tags:
    - 'tcpip,rwin,network-performance'
---
Windows Vista enables [TCP Receive Window Auto-Tuning](/article/vista-tcpip-auto-rwin.html) for all non HTTP traffic.  
  
 RWIN auto-tuning allows Windows to make better use of high network bandwidth to download / stream data faster, but it is not enabled by default for HTTP connections. This is because the HTTP protocol usually travels over the Internet, where bad routers not supporting RWIN auto-tuning can cause a slow or dropped connections.  
  
 It is possible to enable RWIN auto-tuning for Internet Explorer with this DWORD value:

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\InternetSettings\]  
>  TcpAutotuning = 1

 More Info [MS KB947239](http://support.microsoft.com/kb/947239 "Description of the Receive Window Auto-Tuning feature for HTTP traffic on Windows Vista-based computers")