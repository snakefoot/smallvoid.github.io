---
title: 'Make sidebar and gadgets work with UAC disabled'
date: '2009-09-21T00:48:35+02:00'
status: publish
permalink: /article/winnt-sidebar-uac.html
author: Snakefoot
excerpt: 'Windows 7 sidebar will by default not allow applications that requires administrator rights.'
type: post
id: 813
category:
    - Tips
tag:
    - sidebar
    - user-account-control
post_format: []
tags:
    - 'user-account-control,sidebar'
---
If having disabled the security feature [UAC](/article/winnt-user-account-protection.html), then the sidebar and gadgets will stop working (not display).  
  
 Windows 7 enforces the sidebar not to run applications that requires administrator rights, but with UAC disabled, then all applications have administrator rights.  
  
 To fix this issue, create the following DWORD value:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Sidebar \\Settings\]  
>  AllowElevatedProcess = 1

 Credits [MyDigitalLife.info](http://www.mydigitallife.info/2009/01/22/disable-uac-in-windows-7-with-sidebar-and-gadgets-working-properly/)