---
title: 'Restrict access to the registry over the network'
date: '2002-02-03T22:02:56+01:00'
status: publish
permalink: /article/winnt-remote-registry.html
author: Snakefoot
excerpt: 'Manage what accounts that have remote access to the registry.'
type: post
id: 454
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - registry
    - remote-registry
post_format: []
tags:
    - 'remote-registry,registry'
---
By default it is possible to access another computer registry remote. One can control who has remote access to the registry.  
  
 Start RegEdt32.exe and create the following registry-value, then select the winreg-key and set the wanted permissions for those who should have remote access:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\SecurePipeServers \\winreg\]  
>  Description = "Registry Server"

 Note to access the [remote registry service](/article/winnt-services-remoteregistry.html) over the network, just open your registry editor, and in the menu select "Registry" -&gt; "Connect Network Registry"  
  
 Note Windows 2003 blocks for accessing the registry remotely, to remove this block one have to change permissions for "winreg" to allow "Administrators" to have "Full Control" and give "Local Service" access to "Read". More Info [MS KB555335](http://support.microsoft.com/kb/555335 "Can't access "Remote Registry" Service after upgrading to Windows 2003 [Q555335]")  
  
 More Info [MS KB153183](http://support.microsoft.com/kb/153183 "How to Restrict Access to the Registry from a Remote Computer [Q153183]")  
 More Info [MS KB185873](http://support.microsoft.com/kb/185873 "Reg.exe Displays Access Denied Error When Querying Registry [Q185873]")  
 More Info [MS KB310426](http://support.microsoft.com/kb/310426 "HOW TO: Use the Windows XP and Windows Server 2003 Registry Editor Features [Q310426]")  
 More Info [MS KB314837](http://support.microsoft.com/kb/314837 "How to Manage Remote Access to the Registry [Q314837]")  