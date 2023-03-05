---
title: 'Configure the WMI logging level'
date: '2001-03-23T01:18:01+01:00'
status: publish
permalink: /article/winnt-wmi-logging.html
author: Snakefoot
excerpt: 'How to configure the location of WMI logs and how verbose the logs should be.'
type: post
id: 376
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - cimon
    - wbem
    - wmi
post_format: []
tags:
    - 'wbem,wmi,cimon'
---
The [Windows Management Instrumentation service](/article/winnt-services-winmgmt.html) maintains logs with informational-, warning-, error-messages:

> %Windir%\\System32\\Wbem\\Logs\\Wbemcore.log  
>  %Windir%\\System32\\Wbem\\Logs\\Wmiprov.log  
>  %Windir%\\System32\\Wbem\\Logs\\Framework.log

 These logs are mostly necessary for WMI script developers or system administrators when searching for the cause of errors. For the average user these logs makes no sense and can just as well be disabled to avoid unnecessary I/O and defragmentation:
- To configure logging press **Start**-button and **Run...** this command:
  > wmimgmt.msc
- In the **Action**-menu select **Properties**
- In the **Logging**-tab one can configure the logging
- The settings should be reflected in these registry keys:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\WBEM \\CIMOM\]  
  >  Logging = "0" (Errors="1", Verbose="2", Default = "1")  
  >   
  >  Logging Directory = "%windir%\\system32\\wbem\\logs"  
  >   
  >  Log File Max Size = "65536"  
  >   
  >  More Info [MS KB252679](http://support.microsoft.com/kb/252679 "INFO: Tips on WMI Driver Testing [Q252679]")  
  >  More Info [MS KB836605](http://support.microsoft.com/kb/836605 "The Framework.log file grows larger than 64 KB when you use WMI on a Windows XP computer [Q836605]")
 
 Besides the log file the service continuously maintains a database with information about the machine which resides in this folder and subfolders:
 > %Windir%\\System32\\Wbem\\Repository

 Note one can configure the location of this database:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\WBEM \\CIMOM\]  
>  Installation Directory = "%Windir%\\System32\\Wbem"  
>  Working Directory = "%Windir%\\System32\\Wbem"  
>  Repository Directory = "%Windir%\\System32\\Wbem\\Repository"

 Note one can configure the size of this database:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\WBEM \\CIMOM\]  
>  Starting Db Size = "400000"  
>  Max DB Size = "400000"

 Note one can configure the recording of events:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\WBEM \\CIMOM\]  
>  EnableEvents = "0" (Default = "1")

 Credits [Alexander Peter Kowalski (APK)](http://www.avatar.demon.nl/)