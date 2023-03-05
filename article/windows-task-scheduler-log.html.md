---
title: 'Configure the Task Scheduler Log'
date: '2004-07-08T23:54:34+02:00'
status: publish
permalink: /article/windows-task-scheduler-log.html
author: Snakefoot
excerpt: 'How to configure the location and size of the task scheduler log with all its events.'
type: post
id: 288
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - scheduled-task
    - task-scheduler
post_format: []
tags:
    - 'task-scheduler,scheduled-task'
---
The graphical Task Scheduler has its own event log, which can be viewed like this:

1. Open **Control Panel**
2. Double-click the **Scheduled Tasks** folder
3. Select the **Advanced**-item in the menu, and pick **View Log**
 
 This log can be useful to monitor the activity of the Task Scheduler, and can help in diagnosing problems with a scheduled task.  
  
 It is possible to configure the max-size and the location of the log-file:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\SchedulingAgent\]  
>  MaxLogSizeKB = 32 (Default = 32 KBytes)  
>  LogPath = "%windir%\\SchedLgU.Txt"  
>   
>  More Info [MS KB169443](http://support.microsoft.com/kb/169443 "How to Limit the Maximum Size of the Scheduled Tasks Log File [Q169443]")

 Credits [Sanx.org](http://www.sanx.org/)