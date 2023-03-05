---
title: 'Setting up the IIS Services'
date: '2002-03-16T00:11:23+01:00'
status: publish
permalink: /article/win2k-iis-services.html
author: Snakefoot
excerpt: 'Different Microsoft articles telling how to setup a mail-server, news-server, ftp-server or web-server.'
type: post
id: 428
category:
    - Network
tag:
    - ftp
    - ftp-server
    - iis
    - news-server
    - web-server
post_format: []
tags:
    - 'iis,ftp-server,news-server,web-server,ftp'
---
The Internet Information Server(IIS) has several useful services :

- The IIS File Transfer Protocol (FTP) Server, is useful when needing a file server.  
  [HOW TO: Set Up an FTP Server in Windows 2000 (MS KB300662)](http://support.microsoft.com/kb/300662)  
  [Information About the IIS File Transmission Protocol (FTP) Service (MS KB283679)](http://support.microsoft.com/kb/283679)
- The IIS Network News Transfer Protocol (NNTP) Server, is useful when needing a news server.  
  [HOW TO: Set Up and Configure an NNTP Virtual Server in Windows 2000 (MS KB308162)](http://support.microsoft.com/kb/308162)
- The IIS Hyper Text Transport Protocol (HTTP) Server, is useful if wanting a web server to host your homepage.  
  [HOW TO: Configure Windows 2000 as a Web Server (MS KB308192)](http://support.microsoft.com/kb/308192)  
  [HOW TO: Troubleshoot the Web Server in Windows 2000 (MS KB297954)](http://support.microsoft.com/kb/297954)  
  [HOW TO: Troubleshoot ASP in IIS 5.0 in Windows 2000 (MS KB309051)](http://support.microsoft.com/kb/309051)  
  [HOW TO: Optimize Web Server Performance in Windows 2000 (MS KB308186)](http://support.microsoft.com/kb/308186)  
  [HOW TO: Enable IIS Logging Site Activity in Windows 2000 (MS KB300390)](http://support.microsoft.com/kb/300390)  
  [HOW TO: Enable SSL for your web site in IIS (MS KB298805)](http://support.microsoft.com/kb/298805)  
  [HOW TO: Create a New Virtual Web Site with Its Own IP Address in IIS (MS KB300991)](http://support.microsoft.com/kb/300991)  
  [HOW TO: Create a Virtual Folder (Subweb) in IIS 4.0 or IIS 5.0 (MS KB301392)](http://support.microsoft.com/kb/301392)
- The IIS Simple Mail Transfer Protocol (SMTP) Server, is useful when needing a mail server.  
  [HOW TO: Set Up and Configure an SMTP Virtual Server in Windows 2000 (MS KB308161)](http://support.microsoft.com/kb/308161)
- The configuration of ISS can take time, so it is a good idea to save the configuration when done:  
  [HOW TO: Create a Metabase Backup in IIS 5 (MS KB300672)](http://support.microsoft.com/kb/300672)  
  [HOW TO: Use Windows Backup and Recovery Tools to Make a Data Backup of IIS (MS KB301420)](http://support.microsoft.com/kb/301420)  
  [HOW TO: Back Up and Restore IIS 5.0 in Windows 2000 (MS KB302573)](http://support.microsoft.com/kb/302573)
 
 Note IIS in Pro version is by default configured to handle 10 concurrent people browsing. It is possible to increase this limit to 20 (Each client requires 2 connections):
 1. Open a command prompt in this folder:
    > c:\\inetpub\\adminscripts
 2. Execute this command (Max value for Srv. is 2000000000):
    > cscript adsutil.vbs set w3svc/MaxConnections 40
 
 Note IIS keeps the connection open for 5 min, by lowering the timeout it will close the connections quicker, thus giving room for new connections:
 1. Open a command prompt in this folder:
    > c:\\inetpub\\adminscripts
 2. Execute this command: 
  - To lower timeout:
    > cscript adsutil.vbs set w3svc/ConnectionTimeout 60
  - To disable timeout (Closes connection right after request):
    > cscript adsutil.vbs set w3svc/AllowKeepAlive 0
 
 Related [IIS Lockdown](/article/winnt-iis-lockdown.html)