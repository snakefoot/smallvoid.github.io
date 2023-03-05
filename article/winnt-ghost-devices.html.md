---
title: 'Uninstall ghost devices or services using the Device Manager'
date: '2002-10-12T20:21:20+02:00'
status: publish
permalink: /article/winnt-ghost-devices.html
author: Snakefoot
excerpt: 'Description of ghost devices and how they can be removed in safemode.'
type: post
id: 268
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-time
    - device-manager
    - drivers
    - ghost-devices
    - hardware
    - windows-services
post_format: []
tags:
    - 'ghost-devices,device-manager,hardware,drivers,windows-services,boot-time'
---
When one remove hardware or a service, then sometimes Windows thinks that the hardware or service still exists and they roam about as ghost devices in the Device Manager. Ghost devices can cause slow boot and other erratic behavior because Windows tries to communicate with a device which isn't there.

##### Show ghost devices in the Device Manager

1. Open a command prompt (cmd.exe) with administrator rights
2. Set the special [environment variable](/article/winnt-environment-variables.html) with this command:
   > SET DEVMGR\_SHOW\_NONPRESENT\_DEVICES=1
3. Start the Device Manager with this command
   > devmgmt.msc
4. In the Device Manager enable **Show Hidden Devices** in the **View**-menu
 
 Now it should show all devices registered in your system, making it possible to remove any ghosts which shouldn't be there. Devices that are greyed out are inactive(not started), if the same device is listed multiple time then consider removing the inactive ones.  

##### Permanently make the Device Manager show non present devices

 Instead of having to open a command prompt every time, then one can make the [environment variables](/article/winnt-environment-variables.html) permanent, so the Device Manager will always show non-present devices when choosing **Show Hidden Devices**.  
  
 Set the environment variables by adding the following STRING values to the registry:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Environment\]  
>  DEVMGR\_SHOW\_DETAILS = "1"  
>  DEVMGR\_SHOW\_NONPRESENT\_DEVICES = "1"

 More Info [MS KB241257](http://support.microsoft.com/kb/241257 "Device Manager Does Not Display Devices Not Currently Present in Windows 2000 (MS KB241257) [Q241257]")  
 More Info [MS KB304514](http://support.microsoft.com/kb/304514 "How to Configure Device Manager to Display Detailed Information [Q304514]")  
 More Info [MS KB310126](http://support.microsoft.com/kb/310126 "Troubleshooting Device Conflicts with Device Manager [Q310126]")  
 More Info [MS KB315539](http://support.microsoft.com/kb/315539 "Device Manager Does Not Display Devices That Are Not Connected to the Windows XP-Based Computer [Q315539]")  
  
 Credits [regedit.com](http://www.regedit.com/)