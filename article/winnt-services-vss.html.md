---
title: 'Volume Shadow Copy'
date: '2003-06-05T20:22:38+02:00'
status: publish
permalink: /article/winnt-services-vss.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Volume Shadow Copy service.'
type: post
id: 614
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - backup
    - ntbackup
    - volume-shadow-copy
post_format: []
tags:
    - 'backup,volume-shadow-copy,ntbackup'
---
##### Description:

 Volume Shadow Copy Service (VSS) manages and implements Volume Shadow Copies used for backup and other purposes.  
- A computer can be backed up while applications and services are running (Only if the selected files are on a NTFS filesystem)
- Files open at the time of the shadow copy appear closed on the shadow copy volume. (Because the Shadow Copy Volume is an image created from the files selected for backup)
- Files are not skipped during the backup process (Except when not enough available space for creating the Shadow Copy Volume)
- The need for scheduling a backup window is eliminated. A backup window requires that applications be shut down to ensure a successful volume backup.
 
 Note to see the current volume shadow copy backups along with installed shadow copy writers/providers use this command:
 > Vssadmin

 Note if the service is disabled then [NTBackup](/article/winnt-ntbackup.html) will not be able to function and an error will be posted in the Event Log. It is possible to configure Ntbackup to not use Volume Shadow Copy:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\BackupRestore\]  
>  UseMicrosoftProvider = 0  
>   
>  More Info [MS KB833829](http://support.microsoft.com/kb/833829 "The "Disable volume shadow copy" option is unavailable in the Windows Server 2003 backup utility [Q833829]")

 Note if performing a defrag of a volume containing shadow copies, then the defragger can trigger the Volume Shadow Copy service to record all the cluster moving, which will fill the entire shadow copy storage area. VSS will delete the oldest shadow copies to make room, so all or some shadow copies will be lost. Changing the [cluster size](/article/cluster-hard-disk-partition.html) to 16K for the volumes containing shadow copies should solve the problem. More Info [MS KB312067](http://support.microsoft.com/kb/312067 "Shadow copies may be lost when you defragment a volume")  
  
 Note if the Volume Shadow Copy service (VSS) is activated while a defrag is performed, then the defragger might stop before it is completed. VSS is activated when a backup operation is being performed, so either wait for this operation to complete or disable the VSS momentarily while running defrag. Defrag will show this following message while waiting for VSS to finish:
 > Paused for Volume Shadow Copy

 More Info [MS KB838421](http://support.microsoft.com/kb/838421 "How to configure the Shadow Copies of Shared Folders feature on a Windows Server 2003-based server cluster file share [Q838421]")  
 More Info [MS KB887013](http://support.microsoft.com/kb/887013 "How to enable the Volume Shadow Copy service's debug tracing features in Microsoft Windows Server 2003 [Q887013]")  
 More Info [MS Technet - What Is Volume Shadow Copy Service?](http://technet2.microsoft.com/WindowsServer/en/library/3cf204e6-709a-4eb8-8cbc-ad9655de91ba1033.mspx)  
 More Info [MS Technet - How Volume Shadow Copy Service Works](http://technet2.microsoft.com/WindowsServer/en/library/2b0d2457-b7d8-42c3-b6c9-59c145b7765f1033.mspx)  
##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- vssvc.exe (VSS)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)