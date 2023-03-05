---
title: 'Using Internet Explorer as FTP client'
date: '2000-01-01T23:44:18+01:00'
status: publish
permalink: /article/ie-ftp-client.html
author: Snakefoot
excerpt: 'Internet Explorer can be used for simple FTP browsing.'
type: post
id: 315
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
tag:
    - download
    - ftp
    - ftp-client
post_format: []
tags:
    - 'ftp-client,ftp,download'
---
Internet Explorer isn't very obvious in how one should connect to non-public FTP's.  
 If the FTP server requires an account name and password or is using a different port number than the default, then one cannot just write the address for the FTP.  
  
 It is possible to give login/passwd and port number in the url:

> ftp://&lt;login&gt;:&lt;passwd&gt;@www.microsoft.com:&lt;port-number&gt;/

 The login and the passwd is separated with a " : ".  
 There is a " @ " to separate the address from the login and passwd.  
 The port-number is separated from the address with a " : ".  
  
 If only the address is specified, then the Internet Explorer will login as anonymous with no password and connect to port 21.  
  
 Note with Internet Explorer 7 the ability to perform ftp upload has been removed, and one instead have to browse the FTP using Windows Explorer.  
  
 Related [Enable passive FTP mode in Internet Explorer](/article/ie-passive-ftp.html)