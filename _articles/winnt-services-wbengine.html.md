---
title: 'Block Level Backup Engine Service'
date: '2007-07-17T02:12:16+02:00'
permalink: /article/winnt-services-wbengine.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Block Level Backup Engine service.'
type: post
id: 661
categories:
    - windows-vista-services-guide
    - windows-7-win7-services-guide
    - windows-8-win8-services-guide
tags:
    - backup
---
##### Description:

 Used by Windows Backup to perform backup and recovery operations. If this service is stopped by a user, it may cause the currently running backup or recovery operation to fail. Disabling this service may disable backup and recovery operations using Windows Backup on this computer.
 
##### Recommended state:

- Manual

##### Default State:

- Windows 8: Manual
- Windows 7: Manual
- Vista Business/Ultimate: Manual

##### Proces name:

- wbengine.exe (wbengine)

##### Supports:

- none

##### Depends:

- none