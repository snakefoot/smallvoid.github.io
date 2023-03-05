---
title: 'Performance Logs and Alerts'
date: '2000-07-23T15:47:21+02:00'
status: publish
permalink: /article/winnt-services-sysmonlog.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Performance Logs and Alerts service.'
type: post
id: 571
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - performance-counters
    - performance-monitor
post_format: []
tags:
    - 'performance-monitor,performance-counters'
---
##### Description:

 Handles and performance logs and alerts which are configured with Perfmon.exe. The service will stop automatically if there is no performance data to collect.  
  
 Note in Win2k3 this service run in the "Network Service" context, and cannot monitor a performance counter running in "Local System" context (Like SMS). One can handle this by changing the "Log On" properties for this service to "Local System Account".  
  
 Related [Configure performance counters in Win2k/WinXP](/article/winnt-performance-counters.html)  
 Related [Performance Monitor Wizard](http://www.microsoft.com/downloads/details.aspx?FamilyID=31FCCD98-C3A1-4644-9622-FAA046D69214)  
  
 More Info [MS KB127207](http://support.microsoft.com/kb/127207 "Missing Objects and Counters in Performance Monitor [Q127207]")  
 More Info [MS KB130926](http://support.microsoft.com/kb/130926 "Using Performance Monitor to Identify a Pool Leak [Q130926]")  
 More Info [MS KB139609](http://support.microsoft.com/kb/139609 "PerfMon: High Number of Pages/Sec Not Necessarily Low Memory [Q139609]")  
 More Info [MS KB146005](http://support.microsoft.com/kb/146005 "Optimizing Windows NT for Performance [Q146005]")  
 More Info [MS KB150934](http://support.microsoft.com/kb/150934 "How to Create a Performance Monitor Log for NT Troubleshooting [Q150934]")  
 More Info [MS KB164018](http://support.microsoft.com/kb/164018 "Controlling remote Performance Monitor access to Windows NT servers [Q164018]") (Replaces MS KB158438)  
 More Info [MS KB241110](http://support.microsoft.com/kb/241110 ""Computer Name Not Found" Using Performance Monitor [Q241110]")  
 More Info [MS KB244640](http://support.microsoft.com/kb/244640 "Creating Performance Alerts in Windows 2000 [Q244640]")  
 More Info [MS KB248345](http://support.microsoft.com/kb/248345 "How to Create a Log Using System Monitor in Windows 2000 [Q248345]")  
 More Info [MS KB300702](http://support.microsoft.com/kb/300702 ""Unable to Connect to Machine" Error Message When You Try to View Remote Counters [Q300702]")  
 More Info [MS KB300956](http://support.microsoft.com/kb/300956 "How to Manually Rebuild Performance Counter Library Values [Q300956]")  
 More Info [MS KB302558](http://support.microsoft.com/kb/302558 "HOW TO: Create and Configure Performance Monitor Alerts in Windows 2000 [Q302558]")  
 More Info [MS KB324795](http://support.microsoft.com/kb/324795 "HOW TO: Be Reminded When Your Computer Resources Are Running Low in Windows Server 2003 [Q324795]")  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual.

##### Process Name:

- smlogsvc.exe (SysmonLog)

##### Supports:

- None

##### Depends:

- None