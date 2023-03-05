---
title: 'Installing NTBackup in Windows Vista / 2008'
date: '2007-04-24T02:40:01+02:00'
status: publish
permalink: /article/vista-ntbackup-install.html
author: Snakefoot
excerpt: 'Windows Vista / 2008 does not include the NtBackup utility by default.'
type: post
id: 478
category:
    - Troubleshoot
tag:
    - ntbackup
post_format: []
tags:
    - ntbackup
---
Windows Vista includes a completely new backup solution called [Backup and Restore Center](http://www.microsoft.com/windows/windows-vista/features/backup.aspx). It doesn't support BKF-backups made with NTBackup, and it can only make backup of certain filetypes and folders.  
  
 Microsoft has released [Windows NT Backup - Restore Utility](http://www.microsoft.com/downloads/details.aspx?FamilyID=7da725e2-8b69-4c65-afa3-2a53107d54a7), which allows Windows Vista to restore files saved in BKF-files.

> There is a hotfix available to install [Windows NT Backup - Restore Utility](/article/win7-ntbackup-install.html) on Windows 7 / 2008 R2.

##### Installing NTBackup on Windows Vista / 2008

 If having a Windows XP/2003 system around (or look for install cd file nt5backup.cab), then it is possible to copy certain NTBackup files into Windows Vista, which will allow Windows Vista to backup and restore files with NTBackup. Create a new folder on Windows Vista ex. C:\\Program Files\\**NTBackup** and copy the following files from Windows XP to the folder:
- C:Windows\\System32\\Ntbackup.exe
- C:Windows\\System32\\Ntmsapi.dll
- C:Windows\\System32\\Vssapi.dll
- C:Windows\\Help\\Ntbackup.chm
- C:Windows\\Help\\Ntbackup.hlp
 
 Note to run the Restore Utility or NTBackup on Windows Vista, then one has to enable **Removable Storage Management**, or else one will get an NTSMAPI.dll error.
1. Open Control Panel and under "Programs and Features" click "Turn Windows Features on or off"
2. Enable "Removable Storage Management" and press OK
 
 Related [Configure NtBackup for faster throughput](/article/winnt-ntbackup.html)  
  
 Credits [www.petri.co.il](http://www.petri.co.il/)