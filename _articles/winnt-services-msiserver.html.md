---
title: 'Windows Installer'
date: '2000-07-23T21:34:54+02:00'
permalink: /article/winnt-services-msiserver.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Installer service.'
type: post
id: 618
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - microsoft-installer-package
---
##### Description:

 Installs, repairs &amp; removes software according to instructions contained in .MSI files.  
  
 This will allow you to install / uninstall / repair programs listed in the Add/Remove Programs applet in the Control Panel.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20223300%20Q223300" rel="nofollow" title="How to Enable Windows Installer Logging [Q223300]">MS KB223300</a>  
  
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