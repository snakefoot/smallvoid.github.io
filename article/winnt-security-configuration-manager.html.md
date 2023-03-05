---
title: 'Security Configuration Manager Tool'
date: '2003-09-24T18:10:14+02:00'
status: publish
permalink: /article/winnt-security-configuration-manager.html
author: Snakefoot
excerpt: 'Display the security tab for controlling NTFS permissions in Windows XP Home without using safemode.'
type: post
id: 514
category:
    - Utilities
tag:
    - crippled
    - ntfs
post_format: []
tags:
    - 'ntfs,crippled'
---
[Security Configuration Manager](http://www.microsoft.com/ntserver/nts/downloads/recommended/scm/default.asp) can be used in Windows XP Home, so it will show the Security Tab to configure [NTFS permissions](/article/ntfs-access-control.html) for files and folders even when not booting in safemode (WinXP Pro just have to disable [Simple File Sharing](/article/winxp-win9x-filesharing.html#SIMPLE_FILESHARING)).  
  
 To install the package:
1. Download the x86 (Intel) version
2. Double click the **Scesp4i.exe** and extract the contents to a temporary folder
3. Go to the temporary folder and right click **Setup.inf** and select **Install**
4. When the installation is completed reboot the computer
 
 Note it is recommended to create a restore point before installing.  
  
 Note it is possible to disable the Security Tab using system policies (Remove Security tab) or with the registry (NoSecurityTab). More Info [MS KB303153](http://support.microsoft.com/kb/303153 "HOW TO: Remove the Security Tab By Using a Group Policy [Q303153]")  
  
 Credits Gilles Pion