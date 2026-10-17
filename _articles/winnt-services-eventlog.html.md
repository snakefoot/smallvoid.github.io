---
title: 'Windows Event Log'
date: '2000-06-06T03:03:39+02:00'
permalink: /article/winnt-services-eventlog.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Event Log service.'
type: post
id: 544
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
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
 More Info <a href="https://www.bing.com/search?q=KB+172156+Q172156" rel="nofollow" title="How to Delete Corrupt Event Viewer Log Files [Q172156]">MS KB172156</a>  
 More Info <a href="https://www.bing.com/search?q=KB+302542+Q302542" rel="nofollow" title="How To Diagnose System Problems with Event Viewer in Microsoft Windows 2000 [Q302542]">MS KB302542</a>  
 More Info <a href="https://www.bing.com/search?q=KB+308427+Q308427" rel="nofollow" title="HOW TO: View and Manage Event Logs in Event Viewer in Windows XP [Q308427]">MS KB308427</a>  
 More Info <a href="https://www.bing.com/search?q=KB+315410+Q315410" rel="nofollow" title="HOW TO: Use the Event Logging Utility (Logevent.exe) to Create and Log Custom Events in Event Viewer in Windows 2000 [Q315410]">MS KB315410</a>  
  
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