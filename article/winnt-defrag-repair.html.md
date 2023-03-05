---
title: 'Repair the builtin disk defragmenter'
date: '2006-08-24T02:26:37+02:00'
status: publish
permalink: /article/winnt-defrag-repair.html
author: Snakefoot
excerpt: 'The disk defragmenter will fail to load if it not registered properly, or if the services it depends on are disabled.'
type: post
id: 476
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - defrag
post_format: []
tags:
    - defrag
---
##### Symptoms:

 The builtin Disk Defragmenter might stop working if having installed a 3rd party defragger and uninstalled it again.  
  
 When using the [Defrag.exe](/article/winnt-defrag-switches.html) (XP only) command line tool, then it does not start and one gets the following error message:
 > *Windows cannot connect to the Disk Defragmenter engine.*

 When opening **Properties** for a local hard disk, the one either will see a gray **Defragment Now**-button, or when clicking the button one gets the following error message:
 > *The Disk Defragmenter is not installed on your computer. To install it, double-click the Add or Remove Programs icon in Control Panel, click the Install/Uninstall tab, and then follow the instructions on your screen.*

 When trying to open the Disk Defragmenter snapin, then one gets the following error message:
 > *Snap-in failed to initialize,  
 >  CLSID: {43668E21-2636-11D1-A1CE-0080C88593A5}*

##### Solution:

 To repair the Disk Defragmenter execute the following two commands:
 - regsvr32 dfrgsnap.dll
 - regsvr32 dfrgui.dll
 
 If the above actions didn't help, then right click the following file and select **Install**:
 > C:\\Windows\\Inf\\**dfrg.inf**

 Note this issue can also be caused by having disabled the XP SP2 service [DCOM Server Process Launcher](/article/winnt-services-dcomlaunch.html). This service must be configured to Automatic and be running for the Disk Defragmenter to work.  
  
 Note if having disabled or set a low custom size for the [pagefile](/article/windows-page-file.html), then defrag might not work. If using WinXP set the virtual memory to "System Managed Size".  
  
 More Info [MS KB922379](http://support.microsoft.com/kb/922379)  
  
 Credits [AndreasRoom.com](http://andreasRoom.com)