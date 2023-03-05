---
title: 'Configure and troubleshoot Distributed Transaction Coordinator'
date: '2000-07-23T01:21:02+02:00'
status: publish
permalink: /article/winnt-services-msdtc-config.html
author: Snakefoot
excerpt: 'How to reset the transaction log for the Distributed Transaction Coordinator (MSDTC) and reinstall MSDTC.'
type: post
id: 541
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - msdtc
    - reinstall
post_format: []
tags:
    - 'msdtc,reinstall'
---
##### Reinstall MSDTC

 Reinstall the [Distributed Transaction Coordinator](/article/winnt-services-msdtc.html) (MSDTC) with the following steps (Win2k/WinXP/Vista):
1. Execute commands 
  - Net stop msdtc
  - Msdtc -uninstall
2. Delete registry keys:
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft **\\MSDTC\]**  
  >  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services **\\MSDTC\]**
3. Execute commands: 
  - Msdtc -install
  - Msdtc -resetlog
  - Net start msdtc
   
   More Info [MS KB240038](http://support.microsoft.com/kb/240038 "INFO: The "msdtc -remove" Command Shows Errors [Q240038]")  
   More Info [MS KB279786](http://support.microsoft.com/kb/279786 "HOWTO: Reinstall MS DTC for a Nonclustered Windows 2000 Server [Q279786]")  
   More Info [MS KB873160](http://support.microsoft.com/kb/873160 "You may receive a 7391 error message in SQLOLEDB when you run a distributed transaction against a linked server after you install Windows XP Service Pack 2 or Windows XP Tablet PC Edition 2005 [Q873160]")

##### Reset Recovery Log

 [Distributed Transaction Coordinator](/article/winnt-services-msdtc.html) (MSDTC) uses the following log file for storing transaction-related recovery information along with all other MS DTC recovery information (WinNT4 also uses Dtcxatm.log). > %SystemRoot%\\system32\\DTCLog\\MSDTC.LOG

 If the location of the log file is faulty (non existing or no permission) or the MSDTC.LOG is corrupted, then it will keep the service from starting and give errors like:
> *Event ID : 7024  
>  Source : Service Control Manager  
>  Description: The MSDTC service terminated with service specific error 3221229584.  
>   
>  Event ID : 4163  
>  Source : MSDTC  
>  Description: MS DTC log file not found. After ensuring that all Resource Managers coordinated by MS DTC have no indoubt transactions, please run msdtc -resetlog to create the log file.*    
>  More Info [MS KB205069](http://support.microsoft.com/kb/205069 "The Microsoft Distributed Transaction Service Does Not Start and Error 3221229584 Is Logged [Q205069]")

 To reset the log-file :
1. If possible start the computer in safemode
2. Open the **%SystemRoot%\\System32\\DTCLog** folder. (Unless you have changed the default location)
3. If a **Msdtc.log** file exists in the folder, rename it to **Msdtc.old**.
4. Use **Notepad** to save an empty file as **Msdtc.log** in the folder.
5. Open a CMD prompt and type: **msdtc -resetlog** and press Enter.

##### Fix corrupted COM catelog

 The Distributed Transaction Coordinator might fail to perform properly if the [COM+ Catalog](/article/winnt-services-eventsystem.html) have become corrupted.