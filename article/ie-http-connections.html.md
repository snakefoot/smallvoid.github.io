---
title: 'Increase the number of concurrent HTTP connections'
date: '2009-06-17T22:41:28+02:00'
status: publish
permalink: /article/ie-http-connections.html
author: Snakefoot
excerpt: 'Allow multiple downloads and better AJAX performance by increasing HTTP connection limit.'
type: post
id: 788
category:
    - 'Internet Explorer (IE8)'
    - 'Internet Explorer (IE9)'
tag:
    - ajax
    - download
    - network-performance
post_format: []
tags:
    - 'network-performance,download,ajax'
---
In Internet Explorer 7 and earlier, the maximum number of concurrent connections per host process to a single server via HTTP 1.1 is 2. For HTTP 1.0, the limit is 4. IE8 increases the HTTP 1.1 limit to 6.  
  
 The number of http connections affects how many simultaneous downloads one can perform, and the number of simultaneous AJAX requests.  
  
 Create the following DWORD value to configure the connection limit:

> \[HKEY\_CURRENT\_USER \\SOFTWARE \\Microsoft \\Internet Explorer \\MAIN \\FeatureControl \\FEATURE\_MAXCONNECTIONSPERSERVER\]  
>  iexplore.exe = 10

 More Info [AJAX - Connectivity Enhancements in Internet Explorer 8](http://msdn.microsoft.com/en-us/library/cc304129.aspx)  
 More Info [MS KB282402](http://support.microsoft.com/kb/282402 "How do I configure Internet Explorer to download more than two files at one time?")  