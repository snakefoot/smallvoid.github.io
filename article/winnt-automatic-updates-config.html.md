---
title: 'Configure the behavior of the Automatic Updates service'
date: '2002-08-06T23:35:14+02:00'
status: publish
permalink: /article/winnt-automatic-updates-config.html
author: Snakefoot
excerpt: 'Control how and when Automatic Updates (AU) should contact the Windows Update services.'
type: post
id: 524
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - automatic-updates
    - 'Windows Update'
post_format: []
tags:
    - 'windows-update,automatic-updates'
---
[Automatic Updates (AU)](/article/winnt-services-wuauserv.html) uses the following settings as current configuration (Applied when service is started):'
- **Monitor the status of Automatic Updates:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\WindowsUpdate \\Auto Update\]  
  >  DetectionStartTime = "2003.09.10 12:38:10" (Local Time, detection process began)  
  >  LastWaitTimeout= "2003.09.10 11:43:10" (GMT Time, next time to check for updates)  
  >  AUState = 2 (The state of AU for diagnostic)
  > 
  > 
  > - 0 = Initial 24 hour timeout after detecting Internet Connection
  > - 1 = Waiting for user to run AU wizard
  > - 2 = Detect pending (Looking for new patches)
  > - 3 = Download pending (waiting for user to accept pre-download prompt)
  > - 4 = Download in progress
  > - 5 = Install pending (Waiting for install of downloaded patches)
  > - 6 = Install complete
  > - 7 = Disabled (AUOptions will also be set to a value of 0x1)
  > - 8 = Reboot pending (Waiting for reboot required by installed patches)
  > 
  >  More Info [MS KB326693](http://support.microsoft.com/kb/326693 "How to Force Automatic Updates 2.2 to Perform a Detection Cycle [Q326693]")
- **Enable/Disable Automatic Updates:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  NoAutoUpdate = 0 (1 = Disables AU and any controls to configure it)
- **Configure the degree of user interaction:**> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\WindowsUpdate \\Auto Update\]  
  >  AUOptions = 2 (Degree of user interaction)
  > 
  > 
  > - 1 = Disables AU (Same as disabling it through the standard controls)
  > - 2 = Notify Download and Install (Requires Administrator Privileges)
  > - 3 = Notify Install (Requires Administrator Privileges)
  > - 4 = Automatically, no notification (Uses ScheduledInstallTime and ScheduledInstallDay)
  
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  AUOptions = 2 (Degree of user interaction)
  > 
  > 
  > - 2 = Notify Download and Install (Requires Administrator Privileges)
  > - 3 = Notify Install (Requires Administrator Privileges)
  > - 4 = Automatically, no notification (Uses ScheduledInstallTime and ScheduledInstallDay)
- **Configure how often it should check for updates:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  DetectionFrequency = 22 (1-22 Hours between detection)
- **Configure when it should automatically install downloaded updates:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\WindowsUpdate \\Auto Update\]  
  >  ScheduledInstallTime = 0 (0-23 hour of the day)  
  >  ScheduledInstallDay = 0 (1-7 day of the week, 0 = Every day)
  
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  ScheduledInstallTime = 0 (0-23 hour of the day)  
  >  ScheduledInstallDay = 0 (1-7 day of the week, 0 = Every day)  
  >  RescheduleWaitTime = 1 (1-60 minutes to wait after download before installing)
- **Configure when to reboot after installing updates:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  NoAutoRebootWithLoggedOnUsers = 1 (0 = Can reboot while users are logged on)  
  >  RebootWarningTimeoutEnabled = 1 (0 = Force scheduled reboot after 5 minutes, Default = 1)  
  >  RebootWarningTimeout = 5 (Minutes to wait before forcing scheduled reboot, Default = 5)  
  >  RebootRelaunchTimeoutEnabled = 1 (0 = Show the "Restart Later" nag once, Default = 1)  
  >  RebootRelaunchTimeout = 10 (Minutes between the "Restart Later" popups, Default = 10)
- **Enable non-administrators to select "Restart Later" and to start installation before the scheduled time:**
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate\]  
  >  ElevateNonAdmins = 1 (Default = 0)
- **Configure whether to use an internal** [Windows Update Server (WUS)](http://www.wsus.info/) (Formerly known as SUS)
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate \\AU\]  
  >  UseWUServer = 0 (1 = Use Windows Update server specified in WUServer)
  
  > \[HKEY\_LOCAL\_MACHINE \\Software \\**Policies** \\Microsoft \\Windows \\WindowsUpdate\]  
  >  WUServer = "http://intranetsus"  
  >  WUStatusServer = "http://intranetsus"
 
 More Info [MS KB328010](http://support.microsoft.com/kb/328010 "How to configure automatic updates by using Group Policy or registry settings [Q328010]")  