---
title: 'Application Management'
date: '2000-07-23T01:44:13+02:00'
status: publish
permalink: /article/winnt-services-appmgmt.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Application Management service.'
type: post
id: 521
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - group-policy
post_format: []
tags:
    - group-policy
---
##### Description:

 Is used to provide software installation services such as Assign, Publish and Remove. It handles deployment of software for computers joined to a domain through group policies.  
  
 Note Windows XP Home has this service registered, but the appmgmts.dll needed to start the service is not part of Windows XP Home. When installing/uninstalling a program, then the following error will be generated in the Event Log if the service is not disabled:
> *Event ID: 7023  
>  Description: The Application Management Service terminated with the following error: The specified module could not be found.  
>   
>  More Info [MS KB328213](http://support.microsoft.com/kb/328213 "Adding or removing a program may generate Event ID 7023 [Q328213]")*

##### Recommended State:

- Manual

##### Default State:

- Manual

##### Process Name:

- Windows 8 Pro: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AppMgmt)
- Windows 7 Pro: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AppMgmt)
- Vista Business/Ultimate: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AppMgmt)
- WinXP Pro/2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (AppMgmt)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (AppMgmt)

##### Supports:

- None

##### Depends:

- None