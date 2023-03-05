---
title: 'Configure Internet Explorer HTTP send buffer for faster upload'
date: '2006-11-06T20:15:45+01:00'
status: publish
permalink: /article/ie-http-upload.html
author: Snakefoot
excerpt: 'Increase the winsock send buffer to make file uploading faster (Ex. file attachments in webmail).'
type: post
id: 325
category:
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - network-performance
    - send-window
    - tcpip
    - upload
    - winsock
post_format: []
tags:
    - 'tcpip,winsock,upload,send-window,network-performance'
---
Internet Explorer (IE) is able to upload files using the HTTP feature. By default IE uses a send buffer of 8 KBytes, which equals to about 80 KBytes per sec (KBps). It is possible to increase the size of the [winsock send buffer](/article/winnt-winsock-buffer.html), to speed up the uploading of larger files (ex. attaching files in web-mail).  
  
 Configure the size of the send buffer with this DWORD value:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings\]  
>  SocketSendBufferLength = 16384 (Max - 65536)  
>   
>  More info [MS KB329781](http://support.microsoft.com/kb/329781 "HTTP File Upload Operation Takes a Long Time to Complete [Q329781]")

 Note IE 7 does a better job when uploading, and does not require this registry setting.  
  
 Credits [jsifaq.com](http://jsifaq.com/)