---
title: Telnet
date: '2000-07-23T19:30:05+02:00'
status: publish
permalink: /article/winnt-services-telnet.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Telnet service.'
type: post
id: 604
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Allows a remote user to log on to the system and run console programs using the command line. By default this service listens on TCP port 23.  
  
 More Info [MS KB226107](http://support.microsoft.com/kb/226107 "Description of the Registry Entries for the Telnet Server Service [Q226107]")  
 More Info [MS KB233069](http://support.microsoft.com/kb/233069 "HOW TO: Configure Windows 2000 Telnet Service to Not Require NTLM [Q233069]")  
 More Info [MS KB253918](http://support.microsoft.com/kb/253918 "Description of the Telnet Client in Windows 2000 [Q253918]")  
  
##### Recommended State:

- Disabled, for security measures.
- Manual, if wanting to access the system from network through telnet.

##### Default State:

- Win2k/XP: Manual.
- WinXP SP2: Disabled.
- Win2k3: Disabled.

##### Process Name:

- tlntsvr.exe (TlntSvr)

##### Supports:

- None

##### Depends:

- [NT LM Security Support Provider](/article/winnt-services-ntlmssp.html) (WinXP/Win2k3 only)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)