---
title: 'Resultant Set of Policy Provider (RSoP)'
date: '2003-09-21T15:44:20+02:00'
permalink: /article/winnt-services-rsopprov.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Resultant Set of Policy Provider service.'
type: post
id: 586
categories:
    - windows-2003_services
tags: []
---
##### Description:

 Resultant Set of Policy Provider (RSoP) can connect to a Windows domain controller (Windows 2000 or later) and query the group policy configuration from the Windows Management Instrumentation (WMI) database. RSoP can be used for getting an overview of the existing group policy configuration at the different levels (site, domain, domain controller, organizational unit), and for testing the result of changing group policy settings.  
  
 More Info <a href="https://www.bing.com/search?q=KB+304478+Q304478" rel="nofollow" title="Registry Contains a Group Policy Setting That RSoP Does Not Display [Q304478]">MS KB304478</a>  
 More Info <a href="https://www.bing.com/search?q=KB+323276+Q323276" rel="nofollow" title="HOW TO: Install and Use RSoP in Windows Server 2003 [Q323276]">MS KB323276</a>  
  
##### Recommended State:

- Manual.

##### Default State:

- Win2k3: Manual

##### Process Name:

- RSoPProv.exe (RSoPProv)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)