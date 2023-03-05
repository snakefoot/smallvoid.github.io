---
title: 'Run programs elevated without UAC prompt'
date: '2008-10-02T02:44:33+02:00'
status: publish
permalink: /article/winnt-uac-scheduled-task.html
author: Snakefoot
excerpt: 'Launch application with administrator rights without the User Account Protection popup dialog.'
type: post
id: 774
category:
    - 'User Security'
tag:
    - scheduled-task
    - user-account-control
post_format: []
tags:
    - 'user-account-control,scheduled-task'
---
Windows Vista [User Account Protection](/article/winnt-user-account-protection.html) has proven itself as being very effective against malware and their likes.  
  
 When having User Account Control (UAC) enabled, then all programs that requires elevated access will cause a UAC prompt for consent. The UAC prompt for confirmation can be an annoyance if having a special program that one often uses.  
  
 It is possible to avoid the UAC popup dialog if running the program as a Scheduled Task with Administrator privileges. The following steps will create a scheduled task that launches a program, so it automatically gets elevated rights:

1. Open the **Task Scheduler** from Administrative Tools in the Control Panel.
2. Choose to **Create New Task...** in the Task Scheduler Library (Not a basic task). 
  - On the first fan **General** give the task a **Name** and enable the check-box **Run with highest privileges**.
  - On the third fan **Actions** add a **New...** action that starts the program.
  - If wanting the program to be started when a certain event is triggered, then one can create a new trigger on the second fan **Triggers** (At Startup, At Logon, etc.).
3. Press OK button when done.
 
 When having created a scheduled task, then one can activate the scheduled task using the **schtasks.exe** utility:
 > SCHTASKS.EXE /RUN /TN "Name of Task"

 Because **schtasks.exe** is a console utility, then the command prompt window will do a quick flash. This can be solved by creating a shortcut-link to the command-line, and specify on the shortcut-link that it should run minimized.  
  
 Credits [HowToGeek.com](http://www.howtogeek.com/howto/windows-vista/create-administrator-mode-shortcuts-without-uac-prompts-in-windows-vista/ "Create Administrator Mode Shortcuts Without UAC Prompts in Windows Vista")