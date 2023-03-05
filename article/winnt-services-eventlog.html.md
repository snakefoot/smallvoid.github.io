---
title: 'Windows Event Log'
date: '2000-06-06T03:03:39+02:00'
status: publish
permalink: /article/winnt-services-eventlog.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Event Log service.'
type: post
id: 544
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - event-log
post_format: []
tags:
    - event-log
---
##### Description:

 This service tracks events and logs them, which makes it easier to diagnose cause of problems: - **System log**: Contains events from the Windows Operating System, usually a good place to look for a reason when a the system is acting funny
- **Security log**: Contains events from the [Audit watches](/article/winnt-security-audit.html), usually good place to see if someone is attacking your machine
- **Application log**: Contains events from application, usually good place to see 3rd party application events (Though Windows also uses this log)
- **Directory service log** (Win2k3): Contains events from the Windows Active Directory Service
- **File Replication service log** (Win2k3): Contains events from the Windows File Replication service
- **DNS server log** (Win2k3): Contains events from the DNS Server Service
 
 The Event Viewer can be used to view the different logs. Start it through the Control Panel -&gt; Administrative Tools -&gt; Event Viewer.  
  
 Note one can change the location of the log-file for each eventlog:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Eventlog \\**LogName**\]  
>  File = "C:\\Foo\\LogName.Evt"

 Related [Restrict guest access to event logs](/article/winnt-eventlog-guest.html)  
  
 More Info [EventId.net](http://www.eventid.net/ "Look up a specific event id and maybe find its cause")  
 More Info [Events and Errors Message Center](http://www.microsoft.com/technet/support/ee/ee_advanced.aspx)  
 More Info [MS KB172156](http://support.microsoft.com/kb/172156 "How to Delete Corrupt Event Viewer Log Files [Q172156]")  
 More Info [MS KB302542](http://support.microsoft.com/kb/302542 "How To Diagnose System Problems with Event Viewer in Microsoft Windows 2000 [Q302542]")  
 More Info [MS KB308427](http://support.microsoft.com/kb/308427 "HOW TO: View and Manage Event Logs in Event Viewer in Windows XP [Q308427]")  
 More Info [MS KB315410](http://support.microsoft.com/kb/315410 "HOW TO: Use the Event Logging Utility (Logevent.exe) to Create and Log Custom Events in Event Viewer in Windows 2000 [Q315410]")  
  
##### Recommended State:

- Automatic

##### Default State:

- Automatic

##### Process Name:

- [services.exe](/article/winnt-services-wrapper.html) (Eventlog)
- Vista/Win7: [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (Eventlog)

##### Supports:

- [File Replication](/article/winnt-services-ntfrs.html) (Win2k/Win2k3 name)
- [Directory Replicator](/article/winnt-services-ntfrs.html) (WinNT4 name)
- [Task Scheduler](/article/winnt-services-schedule.html) (Vista+)
- [Windows Event Collector](/article/winnt-services-wecsvc.html) (Win7+)
- [Windows Management Instrumentation](/article/winnt-services-winmgmt.html) (WinXP/2k3 only)

##### Depends:

- none