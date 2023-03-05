---
title: 'Activate Application Compatibility-Mode in Windows 2000'
date: '2001-11-03T20:36:57+01:00'
status: publish
permalink: /article/winnt-application-compatibility.html
author: Snakefoot
excerpt: 'Show the "Compatibility"-tab when selecting Properties for a shortcut.'
type: post
id: 389
category:
    - Tips
tag:
    - application-compatibility
post_format: []
tags:
    - application-compatibility
---
Windows 2000 tries to ensure compatibility with applications written for older versions of Microsoft Windows (Ex. Win95,Win98,WinNT4). Many application performs a version check of the operating system to ensure they will be able to work properly. Windows 2000 can trick such an application into thinking that it is being executed on an older version of Windows.  
  
 Microsoft have already created profiles for many old applications, so they will work out of the box with Windows 2000. The administrator can with Windows 2000 Service Pack 2 create own profiles for applications which requires Application Compatibility-Mode.  
  
 To activate the Application Compatibility-Mode interface (When activated a "Compatibility"-tab will appear when selecting Properties for a shortcut):
 > regsvr32 %systemroot%\\apppatch\\slayerui.dll

 To deactivate the Application Compatibility-Mode interface:
 > regsvr32 /u %systemroot%\\apppatch\\slayerui.dll

 More info [MS KB251062](http://support.microsoft.com/kb/251062 "Description of the Application Compatibility Tool [Q251062]")  
 More info [MS KB279792](http://support.microsoft.com/kb/279792 "How to Enable Application Compatibility-Mode Technology in Windows 2000 Service Pack 2 [Q279792]")  
  
 Credits [ntcanuck.com/tq](http://ntcanuck.com/tq/)  