---
title: 'Windows Error Reporting Service'
date: '2007-07-17T02:17:29+02:00'
status: publish
permalink: /article/winnt-services-wersvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Error Reporting Service service.'
type: post
id: 717
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Allows errors to be reported when programs stop working or responding and allows existing solutions to be delivered. Also allows logs to be generated for diagnostic and repair services. If this service is stopped, error reporting might not work correctly and results of diagnostic services and repairs might not be displayed.
 
##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- [svchost.exe -k WerSvcGroup](/article/winnt-services-wrapper.html) (WerSvc)

##### Supports:

- none

##### Depends:

- none