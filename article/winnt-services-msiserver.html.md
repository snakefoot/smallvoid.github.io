---
title: 'Windows Installer'
date: '2000-07-23T21:34:54+02:00'
status: publish
permalink: /article/winnt-services-msiserver.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Installer service.'
type: post
id: 618
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - microsoft-installer-package
post_format: []
tags:
    - microsoft-installer-package
---
##### Description:

 Installs, repairs &amp; removes software according to instructions contained in .MSI files.  
  
 This will allow you to install / uninstall / repair programs listed in the Add/Remove Programs applet in the Control Panel.  
  
 More Info [MS KB223300](http://support.microsoft.com/kb/223300 "How to Enable Windows Installer Logging [Q223300]")  
  
##### Recommended State:

- Manual, if you want to install programs.

##### Default State:

- Manual.

##### Process Name:

- msiexec.exe (MSIServer)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)