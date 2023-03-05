---
title: 'Help and Support Service'
date: '2003-06-05T01:58:41+02:00'
status: publish
permalink: /article/winnt-services-helpsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Help and Support service.'
type: post
id: 547
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 The service supports the Help and Support client application and enables requests from the client application to Microsoft's Help and Support Center.  
  
 Note by default when using Help and Support it will try to access the Internet, to search the Microsoft Knowledge Base articles. This can be annoying for dialup users, but it can be turned off in the **Help and Support Center**, click **Options** -&gt; **Search Options**, and disable the option to search the **MS Knowledge Base**.  
  
 Related [How to repair/reinstall the Help and Support Service](/article/winnt-help-support-service-config.html)  
  
##### Recommended State:

- Manual, if not accessing the Microsoft help by pressing F1 that often.
- Disabled, if not wanting help from microsoft.

##### Default State:

- WinXP/2k3: Automatic.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (helpsvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)