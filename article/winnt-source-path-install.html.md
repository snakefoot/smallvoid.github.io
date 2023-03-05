---
title: 'Change the source path for the install files in Windows NT'
date: '2000-01-01T00:11:27+01:00'
status: publish
permalink: /article/winnt-source-path-install.html
author: Snakefoot
excerpt: 'Configure the path to the location of the install files whether on CD-ROM or HDD.'
type: post
id: 249
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag: []
post_format: []
---
When installing new components then it uses the following registry keys to find the Install-CD:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion\]  
>  Sourcepath = "D:\\i386"  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  Sourcepath= "D:\\"  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  Installation Sources = "D:\\i386" (MULTI\_SZ - Use Regedt32.exe)  
>   
>  More Info [MS KB168645](http://support.microsoft.com/kb/168645 "Error: Please Insert the Compaq SSD into Drive "CD-ROM" [Q168645]")  
>  More Info [MS KB323003](http://support.microsoft.com/kb/323003 "HOW TO: Change the Location of the Installation Files in Windows 2000 [Q323003]")  
>  More Info [MS KB811260](http://support.microsoft.com/kb/811260 "Prompted to Insert Your Windows XP CD-ROM During Setup When the CD-ROM Is in the CD-ROM Drive [Q811260]")  
>  More Info [MS KB833615](http://support.microsoft.com/kb/833615 "The Specify Windows Installation File Location and the Specify Windows Service Pack Installation File Location Group Policy objects do not behave as described on the Explain tab [Q833615]")

 Note that in WinXP one can use the PowerToy TweakUI to configure the source path. My Computer -&gt; Special Folders -&gt; Installation Path.  
  
 Note a new feature have been added to Win2k/WinXP that places the install files from the installed services packs in a backup-folder. This backup-folder is useful in these situations:
- When adding/removing components where the install-CD is used, then one don't have to reinstall the service pack, as the proper install files are available. (Something which caused many problems on WinNT4)
- When [Windows File Protection](/article/winnt-wfp.html) have detected that a protected system file have been deleted or overwritten, then it is able to restore the correct file using the backup-folder.
 
 Therefore if having deleted this backup-folder then Windows will start to complain, but it can be solved by re-installing the service pack. The following registry value specifies the path to the backup-folder (If the latest service pack was slipstreamed to the install CD then it should point to the root of the install CD):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  ServicePackSourcePath = "C:\\WinNt\\ServicePackFiles"  
>   
>  More Info [MS KB271484](http://support.microsoft.com/kb/271484 "Files and Folders Are Added to Your System After Service Pack Is Installed [Q271484]")  
>  More Info [MS KB329260](http://support.microsoft.com/kb/329260 "How to Remove Windows XP Service Pack 1 Folders [Q329260]")

 Note if having changed the install path to a location on the HDD/Network, and don't want to be requested for the install cd, when using [SFC](/article/winnt-sfc.html) or Add/Remove Programs, then one have to set this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  CDInstall = 0  
>   
>  More Info [MS KB316565](http://support.microsoft.com/kb/316565 "INFO: How to Perform an Unattended Installation of Message Queuing Without the Windows 2000 CD [Q316565]")

 Related [Configure Drive Letter for the CD-ROM drive](/article/assign-drive-letter.html)  