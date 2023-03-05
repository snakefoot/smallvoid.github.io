---
title: 'Windows Management Instrumentation (WMI)'
date: '2000-07-23T21:40:16+02:00'
status: publish
permalink: /article/winnt-services-winmgmt.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Management Instrumentation service.'
type: post
id: 619
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - wmi
post_format: []
tags:
    - wmi
---
##### Description:

 Collects and provides system management information by tracking applications and drivers.  
  
 Windows Management Instrumentation(WMI) is an implementation of Distributed Management Task Force's (DMTF) Web-Based Enterprise Management (WBEM).  
 WBEM is a set of open, industry-defined specifications that unify and extend the management of enterprise-computing environment.  
 The central part of WMI is the CIMOM (Common Interface Model Object Manager) which is an interface to the CIM(Common Information Model) also called the WMI repository.  
 WMI makes it possible for drivers, services, applications to return information in form of data or events into the CIM.  
  
 To configure the Windows Management Instrumentation use the following snapin:
 > wmimgmt.msc

 Note if this service is stopped, it will at least have the following effects: - Actions that requires WMI will give errors like:
 > *Interface: Class not registered  
  >   
  >  Win32: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it*
- Unable to see Service Dependencies using Services.msc
- Unable to select Properties for the Computer Management (Local) using CompMgmt.msc
- Unable to see System Information using MsInfo32
- (WinXP) Will experience long delays with [System restore](/article/winnt-services-srservice.html) (Or not work at all)
 
 Related [Disable WBEM logging in Win2k/WinXP](/article/winnt-wmi-logging.html)  
 Related [How to repair WMI when it fails to operate](/article/winnt-wmi-config.html)  
  
 More Info [WMI at MS MSDN](http://msdn.microsoft.com/library/en-us/dnwmi/html/wmicim.asp "Windows Management Instrumentation and the Common Information Model")  
 More Info [WMI at MS Technet](http://www.microsoft.com/technet/prodtechnol/windows2000serv/maintain/featusability/mngwmi.mspx "Managing Windows with WMI")  
 More Info [WMI Diagnosis Utility](http://www.microsoft.com/downloads/details.aspx?FamilyID=d7ba3cd6-18d1-4d05-b11e-4c64192ae97d)  
  
##### Recommended State:

- Automatic, if wanting a fully functioning Windows.

##### Default State:

- Automatic

##### Process Name:

- Win2k: WinMgmt.exe (Winmgmt)
- WinXP/Win2k3/Vista/Win7: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Winmgmt)

##### Supports:

- [Internet Connection Sharing (ICS)](/article/winnt-services-sharedaccess.html) (Vista+)
- [IP Helper](/article/winnt-services-iphlpsvc.html) (Vista+)
- [Security Center](/article/winnt-services-wscsvc.html) (WinXP SP2/Vista+)

##### Depends:

- [Event Log](/article/winnt-services-eventlog.html) (WinXP/Win2k3 only)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)