---
title: 'Interactive Services Detection'
date: '2007-07-17T02:14:04+02:00'
status: publish
permalink: /article/winnt-services-ui0detect.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Interactive Services Detection service.'
type: post
id: 675
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - application-compatibility
post_format: []
tags:
    - application-compatibility
---
##### Description:

 Enables user notification of user input for interactive services, which enables access to dialogs created by interactive services when they appear. If this service is stopped, notifications of new interactive service dialogs will no longer function and there may no longer be access to interactive service dialogs. If this service is disabled, both notifications of and access to new interactive service dialogs will no longer function.  
  
 Since Windows Vista then all drivers and services are isolated in session 0, while other applications are executed in separate sessions (before everything was executed in session 0). If a service in session 0 displays a dialog box, then the interaction will go through this service to reach the user session. The next version of Windows will not include this service, and this service is merely for compatibility until the services are updated to use [WTSSendMessage()](http://msdn2.microsoft.com/en-us/library/aa383842.aspx). More Info [MS WHDC](http://www.microsoft.com/whdc/system/vista/services.mspx "Impact of Session 0 Isolation on Services and Drivers in Windows Vista").
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- UI0Detect.exe (UI0Detect)

##### Supports:

- none

##### Depends:

- none