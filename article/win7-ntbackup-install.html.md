---
title: 'Installing NTBackup on Windows 7 / 2008 R2'
date: '2009-12-26T23:46:39+01:00'
status: publish
permalink: /article/win7-ntbackup-install.html
author: Snakefoot
excerpt: 'Windows 7 / 2008 R2 does not include the NtBackup utility by default.'
type: post
id: 823
category:
    - Troubleshoot
tag:
    - ntbackup
post_format: []
tags:
    - ntbackup
---
NTBackup is no longer available on Windows 7 (Or Vista), and the new "Backup and Restore" system cannot restore old BFK file created by NTBackup.  
  
 Microsoft have now released [Windows NT Backup Restore Utility](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=d9a3d988-bd82-41ca-acf4-39dea08ff7ab) for Windows 7 / 2008 R2, that allows one to restore BFK backup files created with Windows XP NTBackup. More Info [MS KB974674](http://support.microsoft.com/?kbid=974674).

> There is also an official [Windows NT Backup - Restore Utility](/article/vista-ntbackup-install.html) for Windows Vista / 2008.

##### Installing NTBackup on Windows 7 / 2008 R2

 If wanting the original NTBackup on Win7 / Win2k8 R2 then it can be done by creating a new folder on Windows 7 ex. C:\\Program Files\\**NTBackup** and copy the following files from Windows XP to the folder (or extract them from the install file nt5backup.cab):
- C:Windows\\System32\\Ntbackup.exe
- C:Windows\\System32\\Ntmsapi.dll
- C:Windows\\System32\\Vssapi.dll
- C:Windows\\Help\\Ntbackup.chm
- C:Windows\\Help\\Ntbackup.hlp
 
 Note when starting NTBackup then it will complain about "Removable Storage" not running, and this warning can be safely be ignored:
> The Backup Utility cannot connect to the Removable Storage service. This service is required for use of tape drives and other backup devices.  
>   
>  Please exit and start the Removable Storage service using the System Services function of the management console.

 Credits [WinHelpOnline.com](http://www.winhelponline.com/blog/restore-bkf-file-ntbackup-windows-7-vista/)