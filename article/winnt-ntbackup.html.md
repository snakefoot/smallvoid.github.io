---
title: 'Configure NtBackup for faster throughput'
date: '2002-03-17T01:14:28+01:00'
status: publish
permalink: /article/winnt-ntbackup.html
author: Snakefoot
excerpt: 'Increase the size of the buffers used by NtBackup to perform faster backup and restore.'
type: post
id: 253
category:
    - Tips
    - Tips
    - Tips
tag:
    - ntbackup
post_format: []
tags:
    - ntbackup
---
To optimize the performance of NTBackup one can adjust the following registry settings:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Ntbackup \\Backup Engine\]  
>  Logical Disk Buffer Size = "64" (Default 32)  
>  Max Buffer Size = "1024" (Default 512)  
>  Max Num Tape Buffers = "16" (Default 9)  
>   
>  Note one might have to start NTBackup before the default values are created, and one should make sure to create the settings for the user account used for doing the backup.  
>   
>  More Info [Backup Process Used with Clustered Exchange Server 2003 Servers](http://www.microsoft.com/technet/itsolutions/msit/operations/exchbkup.mspx)

 Note Ntbackup is dependent on the service [Removable Storage](/article/winnt-services-ntmssvc.html), and if the service doesn't respond, then Ntbackup will fail to start.  
  
 More Info [MS KB104169](http://support.microsoft.com/kb/104169 "Files That Are Automatically Skipped by the Backup Program (NTBackup.exe) During the Backup and Restore Processes [Q104169]")  
 More Info [MS KB233427](http://support.microsoft.com/kb/233427 "Files and Folders Not Backed Up Using the Ntbackup.exe Tool [Q233427]")  
 More Info [MS KB300439](http://support.microsoft.com/kb/300439 "How to Use Command Line Parameters With the "Ntbackup" Command [Q300439]") (How to use command-line)  
 More Info [MS KB308422](http://support.microsoft.com/kb/308422 "HOW TO: Use Backup to Back Up Files and Folders on Your Computer in Windows XP [Q308422]") (How to backup files)  
 More Info [MS KB309340](http://support.microsoft.com/kb/309340 "HOW TO: Use Backup to Restore Files and Folders on Your Computer in Windows XP [Q309340]") (How to restore files)  
 More Info [MS KB320820](http://support.microsoft.com/kb/320820 "How to Use the Backup Utility to Back Up Files and Folders in Windows XP Home Edition [Q320820]")  
 More Info [MS KB814583](http://support.microsoft.com/kb/814583 "HOW TO: Use Command Line Parameters with the Ntbackup Command in Windows Server 2003 [Q814583]")  
  
 Related [Installing NtBackup in Windows XP Home](/article/winxp-ntbackup-install.html)  
 Related [Installing NtBackup in Windows Vista](/article/vista-ntbackup-install.html)  