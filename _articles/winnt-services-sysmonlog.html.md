---
title: 'Performance Logs and Alerts'
date: '2000-07-23T15:47:21+02:00'
permalink: /article/winnt-services-sysmonlog.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Performance Logs and Alerts service.'
type: post
id: 571
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
tags:
    - performance-counters
    - performance-monitor
---
##### Description:

 Handles and performance logs and alerts which are configured with Perfmon.exe. The service will stop automatically if there is no performance data to collect.  
  
 Note in Win2k3 this service run in the "Network Service" context, and cannot monitor a performance counter running in "Local System" context (Like SMS). One can handle this by changing the "Log On" properties for this service to "Local System Account".  
  
 Related [Configure performance counters in Win2k/WinXP](/article/winnt-performance-counters.html)  
 Related [Performance Monitor Wizard](http://www.microsoft.com/downloads/details.aspx?FamilyID=31FCCD98-C3A1-4644-9622-FAA046D69214)  
  
 More Info <a href="https://www.bing.com/search?q=KB%20127207%20Q127207" rel="nofollow" title="Missing Objects and Counters in Performance Monitor [Q127207]">MS KB127207</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20130926%20Q130926" rel="nofollow" title="Using Performance Monitor to Identify a Pool Leak [Q130926]">MS KB130926</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20139609%20Q139609" rel="nofollow" title="PerfMon: High Number of Pages/Sec Not Necessarily Low Memory [Q139609]">MS KB139609</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20146005%20Q146005" rel="nofollow" title="Optimizing Windows NT for Performance [Q146005]">MS KB146005</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20150934%20Q150934" rel="nofollow" title="How to Create a Performance Monitor Log for NT Troubleshooting [Q150934]">MS KB150934</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20164018%20Q164018" rel="nofollow" title="Controlling remote Performance Monitor access to Windows NT servers [Q164018]">MS KB164018</a> (Replaces MS KB158438)  
 More Info <a href="https://www.bing.com/search?q=KB%20241110%20Q241110" rel="nofollow" title="'Computer Name Not Found' Using Performance Monitor [Q241110]">MS KB241110</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20244640%20Q244640" rel="nofollow" title="Creating Performance Alerts in Windows 2000 [Q244640]">MS KB244640</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20248345%20Q248345" rel="nofollow" title="How to Create a Log Using System Monitor in Windows 2000 [Q248345]">MS KB248345</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20300702%20Q300702" rel="nofollow" title="'Unable to Connect to Machine' Error Message When You Try to View Remote Counters [Q300702]">MS KB300702</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20300956%20Q300956" rel="nofollow" title="How to Manually Rebuild Performance Counter Library Values [Q300956]">MS KB300956</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20302558%20Q302558" rel="nofollow" title="HOW TO: Create and Configure Performance Monitor Alerts in Windows 2000 [Q302558]">MS KB302558</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20324795%20Q324795" rel="nofollow" title="HOW TO: Be Reminded When Your Computer Resources Are Running Low in Windows Server 2003 [Q324795]">MS KB324795</a>  
  
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