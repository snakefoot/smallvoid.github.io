---
title: 'Microsoft Network Diagnostics Tool for Windows NT'
date: '2002-05-27T17:02:42+02:00'
permalink: /article/winnt-netdiag.html
author: Snakefoot
excerpt: 'NetDiag is a command line utility created by Microsoft that can be used diagnose network problems between two computers.'
type: post
id: 508
categories:
    - windows-2000_utilities
    - windows-2003_utilities
    - windows-xp_utilities
tags:
    - network-diagnostic
---
The Network Diagnostics Tool [NetDiag for Windows 2000](http://www.microsoft.com/downloads/release.asp?ReleaseID=22938) can be used to determine the cause of networking problems. More Info <a href="https://www.bing.com/search?q=KB%20265706%20Q265706" rel="nofollow" title="DCDiag and NetDiag in Windows 2000 Facilitate Domain Join and DC Creation [Q265706]">MS KB265706</a> <a href="https://www.bing.com/search?q=KB%20321708%20Q321708" rel="nofollow" title="HOW TO: Use the Network Diagnostics Tool (Netdiag.exe) in Windows 2000 [Q321708]">MS KB321708</a>  
  
 Note if the service [Remote Registry](/article/winnt-services-remoteregistry.html) is not enabled, then one will get the following error:

> *\[FATAL\] Failed to get system information of this machine.*  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20287735%20Q287735" rel="nofollow" title="'[Fatal] Failed to Get System Information' Error Message Occurs When You Run Netdiag [Q287735]">MS KB287735</a>

 Note with Win2k SP4 an [updated version of Netdiag](/tweak/winnt/files/win2ksp4st.htm) has been released. More Info <a href="https://www.bing.com/search?q=KB%20812809%20Q812809" rel="nofollow" title="Windows 2000 SP4 Support Tools [Q812809]">MS KB812809</a>  
  
 Note if using WinXP/Win2k3 one should use the Netdiag.exe supplied on the install cd [WinXP](/tweak/winnt/files/winxpsp2st.htm) (X:\\Support\\Tools\\Setup.exe) / [Win2k3](/tweak/winnt/files/win2k3sp1st.htm) (X:\\Support\\Tools\\suptools.msi), or else one will get the following error:
> *netdiag.exe - Entry Point Not Found :  
>   
>  The procedure entry point DnsIsDynamicRegistrationEnabled could not be located in the dynamic link library DNSAPI.dll  
>  The procedure entry point DnsGetPrimaryDomainName\_UTF8 could not be located in the dynamic link library DNSAPI.dll*