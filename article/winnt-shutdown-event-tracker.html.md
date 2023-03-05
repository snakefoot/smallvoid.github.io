---
title: 'Configure the Shutdown Event Tracker'
date: '2004-07-08T22:41:06+02:00'
status: publish
permalink: /article/winnt-shutdown-event-tracker.html
author: Snakefoot
excerpt: 'The shutdown event tracker forces the user to give a reason for restarting the computer.'
type: post
id: 401
category:
    - Tips
    - Tips
tag:
    - event-log
post_format: []
tags:
    - event-log
---
The Shutdown Event Tracker was created to give a better impression of why the computer is shutdown/restarted, by forcing the user to add a comment about why the shutdown is needed. The Event Log will then contain documentation of what changes that have been applied to the system, which required a shutdown.  
  
 This can be useful for the Administrator, but can be an annoyance for the home user, so it is possible to configure whether one should give a reason for shutting down:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Policies \\Microsoft \\Windows NT \\Reliability\]  
>  ShutdownReasonOn = 0 (WinXP Default = 0, Win2k3 Default = 1)

 Note the [Win2k3 Resource Kit](/article/winnt-resource-kit.html) includes the Custom Reason Editor (Custreasonedit.exe), that allows one to add/change/remove custom reasons for shutting down.  
  
 More Info [MS KB293814](http://support.microsoft.com/kb/293814 "Description of the Shutdown Event Tracker [Q293814]")  
  
 Credits [sanx.org](http://sanx.org/)