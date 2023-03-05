---
title: 'Analyze boot time performance on Vista'
date: '2008-10-04T20:36:29+02:00'
status: publish
permalink: /article/winnt-xperf-xbootmgr.html
author: Snakefoot
excerpt: 'Windows Vista will automatically optimize the boot times, but there can be situations where the boot times remains very slow.'
type: post
id: 776
category:
    - Troubleshoot
tag:
    - boot-time
    - windows-performance-toolkit
post_format: []
tags:
    - 'boot-time,windows-performance-toolkit'
---
Microsoft have created the [Windows Performance Toolkit](https://www.microsoft.com/whdc/system/sysperf/perftools.mspx) (WPT), which can perform several kinds of transition traces to measure the different phases:

- Startup/Boot time tracing
- Shutdown tracing
- Standby/Resume tracing
- Hibernate/Resume tracing
 
 The WPT includes 3 different tools:
- **xbootmgr** - The On/Off Transition Trace Capture tool can capture the transition trace
- **xperf** - The Trace Capture Analysis tool can filter/convert the captured trace
- **xperfview** - The Visual Trace Analysis tool can display the trace data using a graphical representation
 
 To capture a boot trace:
 > xbootmgr -trace boot -noPrepReboot -traceFlags BASE+CSWITCH+DRIVERS+POWER -resultPath C:\\TEMP

 After having captured the trace then one can get a graphical view of the boot process, by starting **xperfview** and browse to the trace-file (\*.etl) in the result path.  
  
 More Info [Windows Performance Toolkit (WPT)](http://msdn.microsoft.com/en-us/library/cc305187.aspx)  
  
 Note before pulling out this big gun to diagnose boot times, then one should check the following to speed up the boot time:
- Open **Problem Reports and Solutions** from the Control Panel and check if have found a solution to your problems.
- Open the **Event Viewer** from Administrative Tools and check for events generated during startup.
- Pull the network cable (disable the network connection) and see if the slow boot times are caused by network timeouts or domain logon authorization.
- Turn off or unplug USB / Bluetooth devices, and see if the long boot times are caused by one of the attached devices.
- Be aware that if having installed Windows Vista on top of Windows XP, then the trouble can be caused by the old XP drivers (It is seldom recommended to perform an upgrade install to Vista). More Info [Clean install of Vista using Upgrade CD](/article/vista-upgrade-install.html)