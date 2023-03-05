---
title: 'WinHTTP Web Proxy Auto-Discovery Service'
date: '2003-09-21T23:39:47+02:00'
status: publish
permalink: /article/winnt-services-winhttpautoproxysvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the WinHTTP Web Proxy Auto Discovery service.'
type: post
id: 623
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The WinHttpAutoSvc implements proxy configuration discovery for WinHttp clients. It performs the lookup done by [WinHttpGetProxyForUrl()](http://msdn.microsoft.com/library/en-us/winhttp/http/winhttpgetproxyforurl.asp). Applications use the service to sandbox autoproxy script execution away from the client process.  
  
 More Info [MSDN - WinHTTP AutoProxy Support](http://msdn.microsoft.com/en-us/library/aa384240.aspx)  
 More Info [Wiki - Web Proxy Autodiscovery Protocol (WPAD)](http://en.wikipedia.org/wiki/Web_Proxy_Autodiscovery_Protocol)  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (WinHttpAutoProxySvc)

##### Supports:

- None

##### Depends:

- [DHCP Client](/article/winnt-services-dhcp.html)