---
title: 'Change the source path for the install files in Windows NT'
date: '2000-01-01T00:11:27+01:00'
permalink: /article/winnt-source-path-install.html
author: Snakefoot
excerpt: 'Configure the path to the location of the install files whether on CD-ROM or HDD.'
type: post
id: 249
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
tags: []
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
>  More Info <a href="https://www.bing.com/search?q=KB%20168645%20Q168645" rel="nofollow" title="Error: Please Insert the Compaq SSD into Drive 'CD-ROM' [Q168645]">MS KB168645</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20323003%20Q323003" rel="nofollow" title="HOW TO: Change the Location of the Installation Files in Windows 2000 [Q323003]">MS KB323003</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20811260%20Q811260" rel="nofollow" title="Prompted to Insert Your Windows XP CD-ROM During Setup When the CD-ROM Is in the CD-ROM Drive [Q811260]">MS KB811260</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20833615%20Q833615" rel="nofollow" title="The Specify Windows Installation File Location and the Specify Windows Service Pack Installation File Location Group Policy objects do not behave as described on the Explain tab [Q833615]">MS KB833615</a>

 Note that in WinXP one can use the PowerToy TweakUI to configure the source path. My Computer -&gt; Special Folders -&gt; Installation Path.  
  
 Note a new feature have been added to Win2k/WinXP that places the install files from the installed services packs in a backup-folder. This backup-folder is useful in these situations:
- When adding/removing components where the install-CD is used, then one don't have to reinstall the service pack, as the proper install files are available. (Something which caused many problems on WinNT4)
- When [Windows File Protection](/article/winnt-wfp.html) have detected that a protected system file have been deleted or overwritten, then it is able to restore the correct file using the backup-folder.
 
 Therefore if having deleted this backup-folder then Windows will start to complain, but it can be solved by re-installing the service pack. The following registry value specifies the path to the backup-folder (If the latest service pack was slipstreamed to the install CD then it should point to the root of the install CD):
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  ServicePackSourcePath = "C:\\WinNt\\ServicePackFiles"  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20271484%20Q271484" rel="nofollow" title="Files and Folders Are Added to Your System After Service Pack Is Installed [Q271484]">MS KB271484</a>  
>  More Info <a href="https://www.bing.com/search?q=KB%20329260%20Q329260" rel="nofollow" title="How to Remove Windows XP Service Pack 1 Folders [Q329260]">MS KB329260</a>

 Note if having changed the install path to a location on the HDD/Network, and don't want to be requested for the install cd, when using [SFC](/article/winnt-sfc.html) or Add/Remove Programs, then one have to set this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Setup\]  
>  CDInstall = 0  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20316565%20Q316565" rel="nofollow" title="INFO: How to Perform an Unattended Installation of Message Queuing Without the Windows 2000 CD [Q316565]">MS KB316565</a>

 Related [Configure Drive Letter for the CD-ROM drive](/article/assign-drive-letter.html)  