---
title: 'Windows XP boot visualizer to analyze the bootup phase'
date: '2002-09-01T15:44:29+02:00'
status: publish
permalink: /article/winxp-bootvis.html
author: Snakefoot
excerpt: 'Microsoft created the tool bootvis for driver developers to see how their driver behaves during bootup.'
type: post
id: 499
category:
    - Utilities
tag:
    - boot-time
    - bootvis
    - logical-prefetcher
post_format: []
tags:
    - 'bootvis,logical-prefetcher,boot-time'
---
[XP Boot Visualizer](http://www.microsoft.com/whdc/hwdev/platform/performance/fastboot/bootvis.mspx) ([Download mirror](http://smallvoid.orgfree.com/?file=bootvis.zip "Bootvis ver. 1.3.37.0 (Without helpfile)")) can monitor what devices are loaded during boot, which is useful for troubleshooting slow booting. It is also able to rearrange the loading of devices to make the bootup faster, though WinXP is already doing this [optimization automatically](/article/winnt-logical-prefetcher.html) every now and then.
- Start BootVis
- The left pane shows the resources which should be traced. Make sure all check-boxes are ticked
- In the menu select "Trace" -&gt; "Next Boot + Drivers Trace"
- A window will popup allowing you to specify how many times to trace. (3 is recommended)
- Let Bootvis reboot your system without interfering.
- Start Bootvis again to analyze the results
- In the menu select "Trace" -&gt; "Optimize System" 
  - Let Bootvis do it things without interfering
- In the menu select "Trace" -&gt; "Stop Tracing" 
  - If not performing this step then the Windows\\System32\\Logfiles\\Wmi\\Trace.log will keep growing for each boot and can get quite large. One can safely delete the Trace.log after this.
 
 Note it is a good idea to create a System Restore Point, before trying this tool as there are several reports of Bootvis actually increasing the boot time (Most get an improvement).  
  
 Note bootvis supports command line options to see them all execute this command:
 > Bootvis /?

 Note that bootvis is dependent on the services [Task Scheduler](/article/winnt-services-schedule.html) and [COM+ Event System](/article/winnt-services-eventsystem.html). If these services are not available this error will popup:
 > *Failed to defrag the system. Try and defrag the system manually*

 Note if one haven't applied at least Service Pack 1 (SP1), then one should use the old version [BootVis-Tool.exe](http://download.microsoft.com/download/whistler/BTV/1.0/WXP/EN-US/BootVis-Tool.exe) ([mirror](http://smallvoid.orgfree.com/?file=bootvis-tool.zip "Bootvis ver. 1.3.36.0")) else one will get the following error with the [new version (MB KB821581)](http://support.microsoft.com/kb/821581 "Performance Trace Data from the BootVis.exe Tool Is Corrupted or Missing [Q821581]") (Bootvis.msi):
 > *The procedure entry point WmiOpenTraceWithCursor could not be located in the dynamic link library ADVAPI32.dll*

 More Info [Fast Boot / Fast Resume Design](http://go.microsoft.com/fwlink/?LinkId=17582)  