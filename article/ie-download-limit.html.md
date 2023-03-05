---
title: 'More than 2 downloads at a time with Internet Explorer'
date: '2000-07-23T13:51:23+02:00'
status: publish
permalink: /article/ie-download-limit.html
author: Snakefoot
excerpt: 'The HTTP 1.1 specification dictates that a browser should only be allowed to have two simultaneous download connections.'
type: post
id: 309
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
tag:
    - download
    - network-performance
post_format: []
tags:
    - 'download,network-performance'
---
When doing downloads with IE and you want to download several files it is a pain that you can only do 2(HTTP 1.1) or 4(HTTP 1.0) at a time. The registry thing below will fix that:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings\]  
>  "MaxConnectionsPer1\_0Server"=dword:00000010  
>  "MaxConnectionsPerServer"=dword:00000008

 When making these changes you will be breaking the HTTP 1.1 specification, and there are rumors that it will cause broken downloads, but those rumors are not true. But in any case make a backup of your current settings before adding these so you can rollback if something bad should happen.  
  
 If you don't want to play with your registry then you can also break the limit by launching several IE's (not with CTRL-N(new) ) but with running iexplore several times. For each iexplore you are allowed to do 2 downloads simultaneously.  
  
 More info [MS KB183110](http://support.microsoft.com/kb/183110 "INFO: WinInet Limits Connections Per Server [Q183110]")