---
title: 'Application Experience'
date: '2007-07-17T02:11:52+02:00'
status: publish
permalink: /article/winnt-services-aelookupsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Application Experience service.'
type: post
id: 658
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

 Processes application compatibility cache requests for applications as they are launched.  
  
 Improves application compatibility by recognizing 3rd party applications that needs special compatibility settings and apply these settings so they run properly.  
  
 More Info [MS KB902196](http://support.microsoft.com/kb/902196 "Description of the Application Experience Lookup Service in Windows Server 2003 SP1") (Added to Windows 2003 with SP1)  
##### Recommended state:

- Windows 8: Manual (Trigger Start)
- Windows 7: Manual
- Windows Vista: Automatic

##### Default State:

- Windows 8: Manual (Trigger Start)
- Windows 7: Manual
- Windows Vista: Automatic

##### Proces name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AeLookupSvc)

##### Supports:

- none

##### Depends:

- none