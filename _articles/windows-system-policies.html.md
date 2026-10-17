---
title: 'Prevent loading of System Policies when logging on to network'
date: '2003-02-21T14:18:11+01:00'
permalink: /article/windows-system-policies.html
author: Snakefoot
excerpt: 'System Policies are useful when wanting to enforce a certain configuration or restriction on all computer and users in the domain.'
type: post
id: 310
categories:
    - windows-95_network
    - windows-98_network
    - windows-me_network
    - windows-nt4_network
    - windows-2000_network
tags:
    - system-policies
    - windows-domain
    - windows-login
---
System Policies is an easy way to hide / lock options to keep the users from rendering the computer useless. The System Policies are configured a central place and are applied when the user logon to the network (They have been replaced with Group Policies).  
  
 One can configure whether a machine should apply the System Policies with this DWORD :

> 0 = Disabled  
>  1 = Automatically search for policy file ntconfig.pol in the Netlogon share  
>  2 = Manual specifying the location of the policy file using NetworkPath value  
>   
>  \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Update\]  
>  UpdateMode = 0 (Default = 1)

 This option makes it possible to logon to the local machine, set the registry key not to load the system policies and then logon to the network without being restricted.  
  
 Note there is an urban legend that setting the value to 0 will make your explorer refresh the folder contents more often. But setting the value to 0 won't do much harm, so it is a pretty harmless legend.  
  
 More Info <a href="https://www.bing.com/search?q=KB+168231+Q168231" rel="nofollow" title="System Policies Are Not Applied in Windows NT [Q168231]">MS KB168231</a>  
 More Info <a href="https://www.bing.com/search?q=KB+274478+Q274478" rel="nofollow" title="Group Policies for Windows 2000 Professional Clients in Windows NT 4.0 Domain or Workgroups [Q274478]">MS KB274478</a>  