---
title: 'Error Reporting Service'
date: '2003-06-05T02:59:08+02:00'
status: publish
permalink: /article/winnt-services-ersvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Error Reporting service.'
type: post
id: 543
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 The Error Reporting Service provides an infrastructure for collecting, storing and reporting kernel mode, operating system and application faults to Microsoft.  
  
 One can configure the Error Reporting by going to Control Panel -&gt; System-Applet -&gt; Advanced-Tab -&gt; Error Reporting-Button.  
  
##### Recommended State:

- Disabled, if not connected to the Internet or if being paranoid and don't want to give detailed information about your computer to Microsoft every time an application crashes.

##### Default State:

- Automatic

##### Process Name:

- WinXP: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (ERSvc)
- Win2k3: [svchost.exe -k WinErr](/article/winnt-services-wrapper.html) (ERSvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)