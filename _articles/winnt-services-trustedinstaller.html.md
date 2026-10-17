---
title: 'Windows Modules Installer'
date: '2007-07-17T02:18:11+02:00'
permalink: /article/winnt-services-trustedinstaller.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Modules Installer service.'
type: post
id: 725
categories:
    - windows-vista_services
    - windows-7-win7_services-guide
tags:
    - automatic-updates
    - windows-update
---
##### Description:

 Enables installation, modification, and removal of Windows updates and optional components. If this service is disabled, you may not be able to install or uninstall Windows updates.  
  
 Used for installing .msu update packages, which is used by Windows Updates.  
  
 Note if disabling this service, then it will also stop [System File Checker](/article/winnt-sfc.html) (SFC) from working, and probably also [Windows File Protection](/article/winnt-wfp.html):
 > Windows Resource Protection could not start the repair service

 Note if the TrustedInstaller.exe process continuously starts up with a high CPU usage (100%) and the harddisk is constantly thrashing, then it can be caused by the Windows component store being corrupt (Windows Update error 80073712). More Info <a href="https://www.bing.com/search?q=KB%20947821%20Q947821" rel="nofollow" title="Description of the System Update Readiness Tool">MS KB947821</a>
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- TrustedInstaller.exe (TrustedInstaller)

##### Supports:

- none

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html)