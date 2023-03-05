---
title: 'Enable passive ftp mode in Internet Explorer'
date: '2000-01-01T00:01:14+01:00'
status: publish
permalink: /article/ie-passive-ftp.html
author: Snakefoot
excerpt: 'Internet Explorer can switch been active ftp and passive ftp mode.'
type: post
id: 316
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
tag:
    - ftp
    - ftp-client
    - passive-ftp
post_format: []
tags:
    - 'ftp-client,passive-ftp,ftp'
---
Internet Explorer has an option to enable passive FTP mode. The active FTP connection is created with the following steps:

1. FTP server listens for command connections on port 21
2. FTP client creates a command connection from port (N &gt; 1024) to the FTP Server port 21
3. FTP client listens for a data connections on port (N+1)
4. FTP server creates a data connection from port 20 to the port (N+1)
 
 This will not work if the FTP client is behind a proxy/firewall/router, as it will deny the connection attempt from the FTP server. The passive FTP connection (PASV) is created with the following steps:
1. FTP server listens for command connections on port 21
2. FTP client creates a command connection from port (N &gt; 1024) to the FTP server port 21
3. FTP server starts listening for a data connection on a random port (P)
4. FTP server sends a PORT P command back to the client with the data connection port
5. FTP client creates a data connection from port (N &gt; 1024) to the FTP server port P
 
 If able to connect to the FTP server, but cannot receive directory listing and getting the error not able to access folder, then it is a good sign that passive mode is required.  
  
 To enable passive FTP open Control Panel -&gt; Internet Options -&gt; Advanced -&gt; "Use Passive FTP for compatibility with some firewalls and DSL modems"  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Ftp\]  
>  Use PASV = "yes"

 Note there is another Advanced option "Enable Folder View for FTP sites" (Sometimes seen as "Use Web Based FTP"). If this option is enabled, then it will ignore the Passive FTP setting and always use Active FTP, but enables one to upload files to the FTP if having the right permissions.  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Ftp\]  
>  Use Web Based FTP = "yes"

 Note some FTP Servers (Like ftp.microsoft.com) doesn't respond back when a client connects passively. Instead one gets the error "425 Can't open data connection".  
  
 Related [Use IE as a FTP client](/article/ie-ftp-client.html)  
  
 More info [MS KB217888](http://support.microsoft.com/kb/217888 "How to Install and Use FTP Folders [Q217888]")  
 More info [MS KB309816](http://support.microsoft.com/kb/309816 "HOW TO: Configure Internet Explorer to Use Both the FTP PORT Mode and PASV Mode [Q309816]")  
 More info [MS KB323446](http://support.microsoft.com/kb/323446 "HOW TO: Configure Internet Explorer to Use Both the FTP PORT Mode and the FTP PASV Mode in the Windows Server 2003 Family [Q323446]")  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)