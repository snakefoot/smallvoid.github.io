---
title: 'Configure NtBackup for faster throughput'
date: '2002-03-17T01:14:28+01:00'
permalink: /article/winnt-ntbackup.html
author: Snakefoot
excerpt: 'Increase the size of the buffers used by NtBackup to perform faster backup and restore.'
type: post
id: 253
categories:
    - windows-2003_tips
    - windows-xp_tips
    - windows-2000_tips
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
  
 More Info <a href="https://www.bing.com/search?q=KB+104169+Q104169" rel="nofollow" title="Files That Are Automatically Skipped by the Backup Program (NTBackup.exe) During the Backup and Restore Processes [Q104169]">MS KB104169</a>  
 More Info <a href="https://www.bing.com/search?q=KB+233427+Q233427" rel="nofollow" title="Files and Folders Not Backed Up Using the Ntbackup.exe Tool [Q233427]">MS KB233427</a>  
 More Info <a href="https://www.bing.com/search?q=KB+300439+Q300439" rel="nofollow" title="How to Use Command Line Parameters With the 'Ntbackup' Command [Q300439]">MS KB300439</a> (How to use command-line)  
 More Info <a href="https://www.bing.com/search?q=KB+308422+Q308422" rel="nofollow" title="HOW TO: Use Backup to Back Up Files and Folders on Your Computer in Windows XP [Q308422]">MS KB308422</a> (How to backup files)  
 More Info <a href="https://www.bing.com/search?q=KB+309340+Q309340" rel="nofollow" title="HOW TO: Use Backup to Restore Files and Folders on Your Computer in Windows XP [Q309340]">MS KB309340</a> (How to restore files)  
 More Info <a href="https://www.bing.com/search?q=KB+320820+Q320820" rel="nofollow" title="How to Use the Backup Utility to Back Up Files and Folders in Windows XP Home Edition [Q320820]">MS KB320820</a>  
 More Info <a href="https://www.bing.com/search?q=KB+814583+Q814583" rel="nofollow" title="HOW TO: Use Command Line Parameters with the Ntbackup Command in Windows Server 2003 [Q814583]">MS KB814583</a>  
  
 Related [Installing NtBackup in Windows XP Home](/article/winxp-ntbackup-install.html)  
 Related [Installing NtBackup in Windows Vista](/article/vista-ntbackup-install.html)  