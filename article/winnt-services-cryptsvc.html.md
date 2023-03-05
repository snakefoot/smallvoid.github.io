---
title: 'Cryptographic Services'
date: '2003-06-05T00:27:11+02:00'
status: publish
permalink: /article/winnt-services-cryptsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Cryptographic services.'
type: post
id: 532
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides 4 types of services: - Catalog Database Service, which confirms the signatures of Windows files (Windows File Protection) and whether drivers are signed correctly (WHQL) and allowing new programs to be installed.
- Protected Root Service, which adds and removes Trusted Root Certification Authority certificates from this computer
- Key Service, which helps enroll this computer for certificates
- **(Vista+)** Automatic Root Certificate Update Service, which retrieves root certificates from Windows Update and enable scenarios such as SSL
 
 Note that Windows Update and Windows File Protection will not work if this service is not set to Automatic, and will complain when manually installing drivers and updates/servicepacks for Windows with the error:
 > *Setup could not verify the integrity of the file Update.inf. Make sure the Cryptographic service is running on this computer*

 Note the database, that contains information of what updates have been applied, can become corrupted and will cause this service to fail. To clear the database execute the following commands (If getting access denied when renaming the directory, then boot in safemode and try again):
1. net stop cryptsvc
2. del /q %systemroot%\\system32\\catroot2\\Edb\*.log
3. del /q %systemroot%\\security\\Edb\*.log
4. net start cryptsvc
 
 Note if this service fails to respond as expected for some reason, then when trying to disable a network connection like Local Area Connection, one will get the following error (Many times a restart will solve the issue):
> *Error Disabling Connection  
>  It is not possible to disable the connection at this time. This connection may be using one or more protocols that do not support Plug-and-Play, or it may have been initiated by another user or the system account.*

 Related [Fix a non-working Windows Update](/article/repair-windows-update.html)  
  
 More Info [MS KB281458](http://support.microsoft.com/kb/281458 "Error Message When You Install a Windows 2000 Service Pack or Product Update [Q281458]")  
 More Info [MS KB316524](http://support.microsoft.com/kb/316524 "You receive an "Administrators only" error message when you try to visit the Windows Update Web site or the Microsoft Update Web site [Q316524]")  
 More Info [MS KB813442](http://support.microsoft.com/kb/813442 "Detecting Digital Signing Issues in Windows XP [Q813442]")  
 More Info [MS KB813444](http://support.microsoft.com/kb/813444 "HOW TO: Troubleshoot Situations Where You Cannot Connect to Secure Web Sites by Using Internet Explorer in Windows XP [Q813444]")  
 More Info [MS KB822798](http://support.microsoft.com/kb/822798 "You Cannot Install Updates or You Are Prompted to Install Updates That You Have Already Installed [Q822798]") (Replaces MS KB326815)  
  
##### Recommended State:

- Automatic

##### Default State:

- Automatic

##### Process Name:

- Win8/Win7/Vista - [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (CryptSvc)
- WinXP/Win2k3 - [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (CryptSvc)

##### Supports:

- [Application Identity](/article/winnt-services-appidsvc.html) (Win7+)
- [Automatic Updates](/article/winnt-services-wuauserv.html) (Unofficial)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)