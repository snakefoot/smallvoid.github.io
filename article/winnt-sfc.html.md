---
title: 'Using the System File Checker in Windows 2000 / XP'
date: '2001-01-26T23:56:55+01:00'
status: publish
permalink: /article/winnt-sfc.html
author: Snakefoot
excerpt: 'System File Checker is able to verify that system files are intact.'
type: post
id: 247
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - system-file-checker
    - system-file-protection
    - system-recovery
post_format: []
tags:
    - 'system-file-checker,system-file-protection,system-recovery'
---
The [Windows File Protection](/article/winnt-wfp.html) is constantly checking whether important files are missing or overwritten and restores them if so. Sometimes it can happen that a file is corrupted anyway, but then one can use the util SFC.EXE with the /SCANNOW option to do a full scan of the critical files and restore those, which have become corrupted:

> SFC /SCANNOW

 Note this operation cannot complete without the install CD. Therefore it is important to insert the install CD before launching the above command. If the install path have changed since the original install, then one have to [change the source path](/article/winnt-source-path-install.html) so SFC can find the install files.  
  
 Note if having applied a service pack, but the contents of the [ServicePackFiles](/article/winnt-source-path-install.html) folder has been deleted or moved, then it will ask you for a CD with the servicepack files. To correct this one should reapply the service pack.  
  
 Note sometimes the WinXP Home will ask for the WinXP Pro CD, but this is not problem as long the above condition have been met. Though it might require that one press Retry several times before the System File Checking begins.  
  
 Note if using Win2k with SP3 or less, then the /SCANNOW will not recognize hotfixes, so they have to be reapplied after running the scan or else you will be using mixed binaries with unpredictable results.  
  
 Note SFC only works when [Windows File Protection (WFP)](/article/winnt-wfp.html) is running. Therefore if booting in **Safemode** or if WFP for some reason won't start, then SFC will fail with an error similar to this:
> *Windows File Protection could not initiate a scan of protected system files.  
>   
>  The specific error code is 0x000006ba \[The RPC server is unavailable.\].*   
>  More Info [MS KB296241](http://support.microsoft.com/kb/296241 "Windows File Protection May Not Start [Q296241]")

 Note to see all options for the System File Checker:
 > SFC /?

 More Info [MS KB222471](http://support.microsoft.com/kb/222471 "Description of the Windows System File Checker Tool [Q222471]")  
 More Info [MS KB310747](http://support.microsoft.com/kb/310747 "Description of Windows XP and Windows Server 2003 System File Checker (Sfc.exe) [Q310747]")  
 More Info [MS KB900910](http://support.microsoft.com/kb/900910 "You are prompted to insert a Windows XP SP2 CD when you try to run the System File Checker tool on a Windows XP SP2-based computer [Q900910]")  
  
 Related [How to configure Windows File Protection](/article/winnt-wfp.html)  