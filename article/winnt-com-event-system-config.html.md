---
title: 'Configure and troubleshoot COM+ Event System service'
date: '2000-07-23T00:17:16+02:00'
status: publish
permalink: /article/winnt-com-event-system-config.html
author: Snakefoot
excerpt: 'How to repair a broken COM+ catalog and reinstall COM+ services.'
type: post
id: 530
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
---
[COM+ Event System](/article/winnt-services-eventsystem.html) will fail to operate if it not having the proper [access rights](/article/ntfs-access-control.html) (Everyone:Read, System:Full, Adminstrators:Full) to the COM+ Catalog (%windir%\\Registration), and will generate the following errors in the Event Log:
> *Event ID: 4609  
>  Description: The COM+ Event System detected a bad return code during its internal processing. HRESULT was 80070005 from line xx of d:\\qxp\_slp\\com\\com1x\\src\\events\\tier1\\eventsystemobj.cpp.  
>   
>  Event ID: 778  
>  Description: Error Code = 0x80004005 : Unspecified error COM+ Services Internals Information: File: d:\\qxp\_slp\\com\\com1x\\src\\shared\\util\\svcerr.cpp, Line: 1259 Comsvcs.dll file version: ENU 2001.12.4414.308 shp  
>   
>  Event ID: 4689  
>  Description: The run-time environment has detected an inconsistency in its internal state. This indicates a potential instability in the process that could be caused by the custom components running in the COM+ application, the components they make use of, or other factors. Error in d:\\qxp\_slp\\com\\com1x\\src\\comsvcs\\package\\cpackage.cpp(1184), hr = 80070005: InitEventCollector failed*   
>  More Info [MS KB909444](http://support.microsoft.com/kb/909444 "Systems that have changed the default Access Control List permissions on the %windir%\registration directory may experience various problems after you install the Microsoft Security Bulletin MS05-051 for COM+ and MS DTC [Q909444]")

 Note if the COM+ Catalog have become corrupt, then it can be re-built with the following steps:
1. Reboot and start in Safemode
2. Open a command prompt (cmd.exe) and execute the following commands: 
   > ren %windir%\\System32\\Clbcatq.dll Clbcatq.dll.bak
   > del %windir%\\Registration\\\*.\* /s
3. Start the registry editor and delete the following registry key:
   > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft **\\COM3**\]
4. Reboot and start in Normal mode.
5. Open a command prompt (cmd.exe) and execute this command:
   > rmdir /s %windir%\\Registration
6. Open the **Control Panel** and double click **Add/Remove Programs**
7. Select **Add/Remove Components** and click **Next** and it will reinstall COM+
8. Re-apply the necessary service packs and updates for COM+.
 
 More Info [MS KB246499](http://support.microsoft.com/kb/246499 "PRB: COM+ Setup Problems While Upgrading to Windows 2000 [Q246499]")  
 More Info [MS KB315296](http://support.microsoft.com/kb/315296 "How to clean up a damaged COM+ catalog [Q315296]")  
 More Info [MS KB318731](http://support.microsoft.com/kb/318731 "Exchange Setup does not work because of a COM+ issue and error code 0xc103798a [Q318731]")  
 More Info [MS KB961938](http://support.microsoft.com/kb/961938 "Error message when you try to sign in to Office Communicator 2007: "Cannot sign in because Communicator cannot subscribe to the System Event Notification Service "")  