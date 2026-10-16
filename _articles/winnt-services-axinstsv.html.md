---
title: 'ActiveX Installer (AxInstSV)'
date: '2009-09-14T22:00:01+02:00'
permalink: /article/winnt-services-axinstsv.html
author: Snakefoot
excerpt: 'Description and recommended settings for the ActiveX Installer (AxInstSV) service.'
type: post
id: 793
categories:
    - windows-vista-services
    - windows-7-win7-services-guide
    - windows-8-win8-services-guide
tags:
    - activex
    - group-policy
---
##### Description:

 Provides User Account Control validation for the installation of ActiveX controls from the Internet and enables management of ActiveX control installation based on Group Policy settings. This service is started on demand and if disabled the installation of ActiveX controls will behave according to default browser settings.  
  
 To install this service on Windows Vista Business/Ultimate:
1. Open **Control Panel** and in the **Programs**-section click **Turn Windows Features On And**.
2. In the Windows Features dialog, select **ActiveX Installer Service**

##### Recommended state:

- Manual

##### Default State:

- Windows 8: Manual
- Windows 7: Manual
- Vista Business/Ultimate: Not installed

##### Proces name:

- [svchost.exe -k AxInstSVGroup](/article/winnt-services-wrapper.html) (AxInstSV)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)