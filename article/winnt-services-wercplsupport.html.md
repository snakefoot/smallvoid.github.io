---
title: 'Problem Reports and Solutions Control Panel Support'
date: '2007-07-17T02:15:40+02:00'
status: publish
permalink: /article/winnt-services-wercplsupport.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Problem Reports and Solutions Control Panel Support service.'
type: post
id: 695
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides support for viewing, sending, and deleting system-level problem reports for the Problem Reports and Solutions control panel.  
  
 To configure or view the reported problems and found solutions go to the Control Panel, navigate to "System and Maintenance" and double click "Problem Reports and Solutions".
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (wercplsupport)

##### Supports:

- none

##### Depends:

- none