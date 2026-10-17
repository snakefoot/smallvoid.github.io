---
title: 'Setting up the IIS Services'
date: '2002-03-16T00:11:23+01:00'
permalink: /article/win2k-iis-services.html
author: Snakefoot
excerpt: 'Different Microsoft articles telling how to setup a mail-server, news-server, ftp-server or web-server.'
type: post
id: 428
categories:
    - windows-2000_network
tags:
    - ftp
    - ftp-server
    - iis
    - news-server
    - web-server
---
The Internet Information Server(IIS) has several useful services :

- The IIS File Transfer Protocol (FTP) Server, is useful when needing a file server.  
  <a href="https://www.bing.com/search?q=KB+300662+Q300662" rel="nofollow">HOW TO: Set Up an FTP Server in Windows 2000 (MS KB300662)</a>  
  <a href="https://www.bing.com/search?q=KB+283679+Q283679" rel="nofollow">Information About the IIS File Transmission Protocol (FTP) Service (MS KB283679)</a>
- The IIS Network News Transfer Protocol (NNTP) Server, is useful when needing a news server.  
  <a href="https://www.bing.com/search?q=KB+308162+Q308162" rel="nofollow">HOW TO: Set Up and Configure an NNTP Virtual Server in Windows 2000 (MS KB308162)</a>
- The IIS Hyper Text Transport Protocol (HTTP) Server, is useful if wanting a web server to host your homepage.  
  <a href="https://www.bing.com/search?q=KB+308192+Q308192" rel="nofollow">HOW TO: Configure Windows 2000 as a Web Server (MS KB308192)</a>  
  <a href="https://www.bing.com/search?q=KB+297954+Q297954" rel="nofollow">HOW TO: Troubleshoot the Web Server in Windows 2000 (MS KB297954)</a>  
  <a href="https://www.bing.com/search?q=KB+309051+Q309051" rel="nofollow">HOW TO: Troubleshoot ASP in IIS 5.0 in Windows 2000 (MS KB309051)</a>  
  <a href="https://www.bing.com/search?q=KB+308186+Q308186" rel="nofollow">HOW TO: Optimize Web Server Performance in Windows 2000 (MS KB308186)</a>  
  <a href="https://www.bing.com/search?q=KB+300390+Q300390" rel="nofollow">HOW TO: Enable IIS Logging Site Activity in Windows 2000 (MS KB300390)</a>  
  <a href="https://www.bing.com/search?q=KB+298805+Q298805" rel="nofollow">HOW TO: Enable SSL for your web site in IIS (MS KB298805)</a>  
  <a href="https://www.bing.com/search?q=KB+300991+Q300991" rel="nofollow">HOW TO: Create a New Virtual Web Site with Its Own IP Address in IIS (MS KB300991)</a>  
  <a href="https://www.bing.com/search?q=KB+301392+Q301392" rel="nofollow">HOW TO: Create a Virtual Folder (Subweb) in IIS 4.0 or IIS 5.0 (MS KB301392)</a>
- The IIS Simple Mail Transfer Protocol (SMTP) Server, is useful when needing a mail server.  
  <a href="https://www.bing.com/search?q=KB+308161+Q308161" rel="nofollow">HOW TO: Set Up and Configure an SMTP Virtual Server in Windows 2000 (MS KB308161)</a>
- The configuration of ISS can take time, so it is a good idea to save the configuration when done:  
  <a href="https://www.bing.com/search?q=KB+300672+Q300672" rel="nofollow">HOW TO: Create a Metabase Backup in IIS 5 (MS KB300672)</a>  
  <a href="https://www.bing.com/search?q=KB+301420+Q301420" rel="nofollow">HOW TO: Use Windows Backup and Recovery Tools to Make a Data Backup of IIS (MS KB301420)</a>  
  <a href="https://www.bing.com/search?q=KB+302573+Q302573" rel="nofollow">HOW TO: Back Up and Restore IIS 5.0 in Windows 2000 (MS KB302573)</a>
 
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