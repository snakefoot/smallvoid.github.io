---
title: 'Configure and troubleshoot Automatic Updates'
date: '2007-08-28T02:02:54+02:00'
status: publish
permalink: /article/winnt-automatic-updates-repair.html
author: Snakefoot
excerpt: 'Troubleshoot and repair Automatic Updates when it fails to perform Windows Update.'
type: post
id: 734
category:
    - Troubleshoot
    - Troubleshoot
tag:
    - automatic-updates
    - 'Windows Update'
post_format: []
tags:
    - 'automatic-updates,windows-update'
---
##### Automatic Updates uses 100% CPU

 [Automatic Updates (AU)](/article/winnt-services-wuauserv.html) can become corrupted, so svchost.exe starts using 100% CPU when contacting Microsoft to check for updates. This can be tested by running this command:
  > wuauclt /detectnow

 To fix the high CPU usage apply the following updates to Automatic Updates. More Info [MS KB932494](http://support.microsoft.com/kb/932494 "When you use Automatic Updates to scan for updates or to apply updates to applications that use Windows Installer, you experience issues that involve the Svchost.exe process"):
- Download and apply [MS KB927891](http://support.microsoft.com/kb/927891 "You receive an access violation error and the system may appear to become unresponsive when you try to install an update from Windows Update or from Microsoft Update") hotfix.
- Download and apply [WindowsUpdateAgent30-x86.exe](http://go.microsoft.com/fwlink/?LinkID=91237) client update for Windows Update Server 3.0 using the **/wuforce** command line switch.

##### Automatic Updates crashes when checking for updates

 Automatic Updates can also enter a state where it crashes by just checking for updates:
 > Generic Host Process for Win32 Services encountered a problem and needed to close.

 To repair the Automatic Updates service try the following steps:
1. Press the Start-button and Run... this command to stop the service:
   > net stop wuauserv
2. Check the root for all drives (including network drives) and delete the folder called **WuTemp**:
   > drive:\\WuTemp
3. Delete the following folder containing the [Cryptographic Service](/article/winnt-services-cryptsvc.html) database:
   > %systemroot%\\system32\\catroot2
4. Rename the following folder to **SoftwareDistributionOLD**:
   > %systemroot%\\SoftwareDistribution
5. Rename the following system files used by Automatic Updates, so [Windows File Protection](/article/winnt-wfp.html) is activated and restores them again: 
  - Cdm.dll
  - Iuengine.dll
  - Wuapi.dll
  - Wuauclt.exe
  - Wuauclt1.exe
  - Wuaucpl.cpl
  - Wuaueng.dll
  - Wuaueng1.dll
  - Wuauserv.dll
  - Wucltui.dll
  - Wups.dll
  - Wups2.dll
  - Wuweb.dll
6. Restart Windows
7. Reinstall [Windows Update Client](http://go.microsoft.com/fwlink/?LinkID=91237) by launching the install with the parameter **/wuforce**
 
 More Info [MS KB916259](http://support.microsoft.com/kb/916259 "Windows Update Web site and the Microsoft Update Web site do not scan for updates when you repair a failed installation")  
 More Info [MS KB931852](http://support.microsoft.com/kb/931852 "Error messages when you start a Windows XP-based computer and then try to download Windows Updates")  
##### Automatic Updates fails to start

 Automatic Updates might fail to start with the following error even if the service is not disabled:
> Error 1058: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it.  
>   
>  Event ID: 10005  
>  DCOM got error "The service cannot be started, either because it is disabled or because it has no enabled devices associated with it. " attempting to start the service wuauserv with arguments "" in order to run the server: {E60687F7-01A1-40AA-86AC-DB1CBF673334}

 This can be caused by the service being disabled with group policies or registry [NoAutoUpdate](/article/winnt-automatic-updates-config.html). It can also be caused by DLL's required by Automatic Updates needs to be registered:
- REGSVR32 %windir%\\system32\\wuapi.dll
- REGSVR32 %windir%\\system32\\wuaueng1.dll
- REGSVR32 %windir%\\system32\\wuaueng.dll
- REGSVR32 %windir%\\system32\\wucltui.dll
- REGSVR32 %windir%\\system32\\wups.dll
- REGSVR32 %windir%\\system32\\Wuauserv.dll