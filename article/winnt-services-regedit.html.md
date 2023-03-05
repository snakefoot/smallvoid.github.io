---
title: 'Using the registry editor to change the service state'
date: '2003-12-31T03:10:28+01:00'
status: publish
permalink: /article/winnt-services-regedit.html
author: Snakefoot
excerpt: 'How to use the registry editor to configure the state of the Windows services.'
type: post
id: 633
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - regedit
    - windows-services
post_format: []
tags:
    - 'regedit,windows-services'
---
1. Start the Registry Editor by pressing the **Start**-button and **Run...** this command:
   > Regedit
2. Browse through the left tree to where **Services** are found:
   > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\**Services**\]

   ![Regedit Service]({{ 'assets/images/regedit_services.jpg' | relative_url }})
  
3. Within the **Services**-key find go to the short-name of the wanted service (Here **RpcSS** aka. [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)):  
    
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\**RpcSS**\]

   ![Regedit RpcSS]({{ 'assets/images/regedit_rpcss.jpg' | relative_url }})
  
4. Double-Click the **Start**-value in the list to the right.  
    
   ![Regedit Value]({{ 'assets/images/regedit_editvalue.jpg' | relative_url }})

5. Change **Value data:** to the wanted state: 
  - 0 = Boot
  - 1 = System
  - 2 = Automatic
  - 3 = Manual
  - 4 = Disabled
6. Press **Ok** and exit the Registry Editor.
7. If setting a service to **Disabled** or **Manual**, then execute this command to stop the service:
   > Net Stop **RpcSS**
8. If setting the service to **Automatic**, then execute this command to start the service:
   > Net Start **RpcSS**
 
 Note in this guide the short-name of a service is shown just in parenthesis next to the "Process Name".  
  
 Note the "Automatic" startup mode was extended with "Automatic (Delayed Start)" with Windows Vista/2008. It specifies that the service startup can be delayed until after having performed user logon. It can be activated with the following DWORD registry setting:
 >  \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\RpcSS\]  
 >  DelayedAutoStart = 1  
 >  Start = 2

 Note the "Manual" startup mode was extended with "Manual (Trigger Start)" with Windows 7/2008 R2. It specifies that the service startup can be delayed until a certain event occurs (or be stopped). See what [service trigger events](http://msdn.microsoft.com/en-us/library/windows/desktop/dd405513.aspx) that are configured for a service with this command:
 > sc qtriggerinfo w32time

   
 More Info [MS KB103000](http://support.microsoft.com/kb/103000 "CurrentControlSet\Services Subkey Entries [Q103000]")  
 More Info [MS KB271362](http://support.microsoft.com/kb/271362 "How to Find the Short Names of Services [Q271362]")  
 More Info [MS KB838428](http://support.microsoft.com/kb/838428 ""Could not start the Remote Procedure Call (RPC) Service. Error 1058" error message when you manually start the Remote Procedure Call service [Q838428]") (About hardware profiles)  