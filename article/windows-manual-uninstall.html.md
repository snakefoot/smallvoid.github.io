---
title: 'Manually remove programs from the Add/Remove list'
date: '2003-06-22T11:16:33+02:00'
status: publish
permalink: /article/windows-manual-uninstall.html
author: Snakefoot
excerpt: 'How to manually uninstall an application and remove it from the Add/Remove list.'
type: post
id: 236
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - control-panel
    - free-disk-space
    - uninstall
post_format: []
tags:
    - 'uninstall,control-panel,free-disk-space'
---
When installing an application in Windows, then it is the application (or user) that is responsible for knowing what changes are made during the install. Most applications are installed by using some sort of installer-software, which performs the logging of the changes made during the install, so it can revert them when uninstalled. Some times the installer-software for the application doesn't do this job properly, or the application makes changes after the install which the installer-software have no chance to know about.  
  
 Therefore when uninstalling an application using the **Add/Remove Programs** applet from the Control Panel, then it might not work as expected. The application might refuse to uninstall if the folder where the application resided has been moved or deleted, or the application continues to stay in the Add/Remove-list even after the uninstall. If one wants to repair/remove entries in the Add/Remove-list, then one can find and remove the entries at this registry location:

> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Uninstall\]

 Note if an application refuses to be uninstalled for whatever reason, then it might be solved by just installing the application again on top of the existing install. This sometimes fixes the uninstall information, so one can remove it without problems.  
  
 If an application still refuses to uninstall, or if the application have been "uninstalled", but haven't been deleted properly, then one have to manually remove the program (Though one is seldom is able to remove it entirely):
1. Make a backup of the registry
2. Shutdown the application, if it is running (If WinNT+ check also for services)
3. Search the registry for any references to the directory where the application resides, and remove them
4. Search the registry for any references to the name of the application, and remove them
5. The following registry places are good candidates for finding leftovers from uninstalled programs:
  > \[HKEY\_CURRENT\_USER \\Software \\&lt;ApplicationName&gt;\]  
  >  \[HKEY\_LOCAL\_MACHINE \\Software \\&lt;ApplicationName&gt;\]  
  >  \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\SharedDLLs\]
6. Rename the directory in which the application was installed in the first place
7. Reboot and if everything goes well, then delete the renamed directory
 
 More Info [MS KB247501](http://support.microsoft.com/kb/247501 "How to Manually Remove Programs from the Add/Remove Programs List [Q247501]")  
 More Info [MS KB247515](http://support.microsoft.com/kb/247515 "Program Is Not Listed in Add/Remove Programs After Installation [Q247515]")  
 More Info [MS KB290301](http://support.microsoft.com/kb/290301 "Description of the Windows Installer CleanUp Utility [Q290301]") (Windows Installer CleanUp Utility)  