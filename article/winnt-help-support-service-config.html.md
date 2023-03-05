---
title: 'Configure and troubleshoot Help and Support Service'
date: '2003-06-05T02:04:03+02:00'
status: publish
permalink: /article/winnt-help-support-service-config.html
author: Snakefoot
excerpt: 'How to reinstall the Help and Support service if it fails to function properly.'
type: post
id: 548
category:
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
tags:
    - ''
---
If having problems with the [Help and Support service](/article/winnt-services-helpsvc.html), then one can try repair it:

- Re-Install the Help and Support service: 
  1. Right this file and in the context menu select "Install" (Remember to enable hidden files and folders):
     > %windir%\\inf\\pchealth.inf
- Re-initialize the Help and Support data storage: 
  1. Press CTRL+SHIFT+ESC to start the Task Manager (TaskMgr.exe)
  2. Select the **Process**-tab and stop the following processes (If they exist):
      > helpsvc.exe  
      > helphost.exe  
      > helpctr.exe
  3. Open a command prompt (Press **Start**-button, **Run...** and open **cmd**) and perform the following commands: 
      1. net stop helpsvc
      2. rmdir %windir%\\pchealth\\helpctr\\packagestore /s /q
      3. rmdir %windir%\\pchealth\\helpctr\\installedskus /s /q
      4. start /w %windir%\\pchealth\\helpctr\\binaries\\helpsvc /svchost netsvcs /regserver /install
      5. start /w %windir%\\pchealth\\helpctr\\binaries\\helpsvc /register
- [Re-Install Internet Explorer in Windows XP](/article/winnt-reinstall-ie.html)
- Delete the HTML Help database file (HH.DAT). More Info [MS KB192915](http://support.microsoft.com/kb/192915 "PRB: Cannot Start the MSDN Library [Q192915]")