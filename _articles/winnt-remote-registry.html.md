---
title: 'Restrict access to the registry over the network'
date: '2002-02-03T22:02:56+01:00'
permalink: /article/winnt-remote-registry.html
author: Snakefoot
excerpt: 'Manage what accounts that have remote access to the registry.'
type: post
id: 454
categories:
    - windows-2003_user-security
    - windows-nt4_user-security
    - windows-xp_user-security
    - windows-2000_user-security
tags:
    - registry
    - remote-registry
---
By default it is possible to access another computer registry remote. One can control who has remote access to the registry.  
  
 Start RegEdt32.exe and create the following registry-value, then select the winreg-key and set the wanted permissions for those who should have remote access:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\SecurePipeServers \\winreg\]  
>  Description = "Registry Server"

 Note to access the [remote registry service](/article/winnt-services-remoteregistry.html) over the network, just open your registry editor, and in the menu select "Registry" -&gt; "Connect Network Registry"  
  
 Note Windows 2003 blocks for accessing the registry remotely, to remove this block one have to change permissions for "winreg" to allow "Administrators" to have "Full Control" and give "Local Service" access to "Read". More Info <a href="https://www.bing.com/search?q=KB+555335+Q555335" rel="nofollow" title="Can't access 'Remote Registry' Service after upgrading to Windows 2003 [Q555335]">MS KB555335</a>  
  
 More Info <a href="https://www.bing.com/search?q=KB+153183+Q153183" rel="nofollow" title="How to Restrict Access to the Registry from a Remote Computer [Q153183]">MS KB153183</a>  
 More Info <a href="https://www.bing.com/search?q=KB+185873+Q185873" rel="nofollow" title="Reg.exe Displays Access Denied Error When Querying Registry [Q185873]">MS KB185873</a>  
 More Info <a href="https://www.bing.com/search?q=KB+310426+Q310426" rel="nofollow" title="HOW TO: Use the Windows XP and Windows Server 2003 Registry Editor Features [Q310426]">MS KB310426</a>  
 More Info <a href="https://www.bing.com/search?q=KB+314837+Q314837" rel="nofollow" title="How to Manage Remote Access to the Registry [Q314837]">MS KB314837</a>  