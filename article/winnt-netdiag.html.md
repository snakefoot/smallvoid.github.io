---
title: 'Microsoft Network Diagnostics Tool for Windows NT'
date: '2002-05-27T17:02:42+02:00'
status: publish
permalink: /article/winnt-netdiag.html
author: Snakefoot
excerpt: 'NetDiag is a command line utility created by Microsoft that can be used diagnose network problems between two computers.'
type: post
id: 508
category:
    - Utilities
    - Utilities
    - Utilities
tag:
    - network-diagnostic
post_format: []
tags:
    - network-diagnostic
---
The Network Diagnostics Tool [NetDiag for Windows 2000](http://www.microsoft.com/downloads/release.asp?ReleaseID=22938) can be used to determine the cause of networking problems. More Info [MS KB265706](http://support.microsoft.com/kb/265706 "DCDiag and NetDiag in Windows 2000 Facilitate Domain Join and DC Creation [Q265706]") [MS KB321708](http://support.microsoft.com/kb/321708 "HOW TO: Use the Network Diagnostics Tool (Netdiag.exe) in Windows 2000 [Q321708]")  
  
 Note if the service [Remote Registry](/article/winnt-services-remoteregistry.html) is not enabled, then one will get the following error:

> *\[FATAL\] Failed to get system information of this machine.*  
>   
>  More Info [MS KB287735](http://support.microsoft.com/kb/287735 ""[Fatal] Failed to Get System Information" Error Message Occurs When You Run Netdiag [Q287735]")

 Note with Win2k SP4 an [updated version of Netdiag](/tweak/winnt/files/win2ksp4st.htm) has been released. More Info [MS KB812809](http://support.microsoft.com/kb/812809 "Windows 2000 SP4 Support Tools [Q812809]")  
  
 Note if using WinXP/Win2k3 one should use the Netdiag.exe supplied on the install cd [WinXP](/tweak/winnt/files/winxpsp2st.htm) (X:\\Support\\Tools\\Setup.exe) / [Win2k3](/tweak/winnt/files/win2k3sp1st.htm) (X:\\Support\\Tools\\suptools.msi), or else one will get the following error:
> *netdiag.exe - Entry Point Not Found :  
>   
>  The procedure entry point DnsIsDynamicRegistrationEnabled could not be located in the dynamic link library DNSAPI.dll  
>  The procedure entry point DnsGetPrimaryDomainName\_UTF8 could not be located in the dynamic link library DNSAPI.dll*