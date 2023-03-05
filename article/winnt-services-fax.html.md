---
title: FAX
date: '2000-01-06T03:13:43+01:00'
status: publish
permalink: /article/winnt-services-fax.html
author: Snakefoot
excerpt: 'Description and recommended settings for the FAX service.'
type: post
id: 546
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - fax
post_format: []
tags:
    - fax
---
##### Description:

 Helps you to send &amp; receive faxes.  
 This service gets installed if fax capable modem is installed in your machine.  
  
 Note in Windows XP the service can be installed by opening the Control Panel -&gt; Add or Remove Programs -&gt; Add/Remove Windows Components -&gt; Check "Fax Services".  
  
 Note in Windows Vista/7 the service can be installed through the Control Panel -&gt; Programs -&gt; Programs and features -&gt; Turn Windows Features on or off.  
  
 More Info [MS KB229827](http://support.microsoft.com/kb/229827 "Description of Event IDs for the Microsoft Fax Service [Q229827]")  
 More Info [MS KB231577](http://support.microsoft.com/kb/231577 "How to Set Permissions for the Fax Service in Windows 2000 [Q231577]")  
 More Info [MS KB306550](http://support.microsoft.com/kb/306550 "HOW TO: Enable and Configure the Fax Service [Q306550]")  
  
##### Recommended State:

- Manual (If having a FAX).

##### Default State:

- Manual (Default not installed)

##### Process Name:

- Win7/XP/Vista/Win2k: fxssvc.exe (FAX)
- WinNT4: faxsvc.exe (FAX)

##### Supports:

- None

##### Depends:

- [Plug And Play](/article/winnt-services-plugplay.html)
- [Print Spooler](/article/winnt-services-spooler.html) (Win2k/WinXP/Vista name)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Spooler](/article/winnt-services-spooler.html) (WinNT4 name)
- [Telephony](/article/winnt-services-tapisrv.html)