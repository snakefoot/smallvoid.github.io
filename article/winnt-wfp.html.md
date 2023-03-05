---
title: 'Using Windows File Protection in Windows 2000 / XP'
date: '2001-01-21T00:05:43+01:00'
status: publish
permalink: /article/winnt-wfp.html
author: Snakefoot
excerpt: 'Windows File Protection is able to keep the system files intact when overwritten.'
type: post
id: 248
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - system-file-protection
post_format: []
tags:
    - system-file-protection
---
The Windows file protection(WFP) is made to avoid overwriting DLLs with older version when installing 3rd party programs. The WFP works the following way :

- The WFP monitors when files are deleted or replaced.
- The WFP checks if the deleted or replaced file is part of its catalog of protected files.
- The WFP checks if the signature of the changed file matches the one stored in the catalog.
- The WFP restores an old copy of the file if the signature doesn't match or the file is just deleted.
- The WFP searches for the old copy in the following order: 
  - C:\\WinNT\\System32\\DLLCACHE
  - [C:\\WinNT\\ServicePackFiles](/article/winnt-source-path-install.html)
  - [&lt;Install-path&gt;\\i386](/article/winnt-source-path-install.html)
 
 To replace a protected file:
1. Copy the file to the DLLCACHE folder (Overwrite if necessary)
2. Delete the actual file
3. WFP will detect the change and restore it from the DLLCACHE folder.
 
 To delete a protected file:
1. Delete the file from the DLLCACHE folder (If it exists)
2. Delete the file from the SERVICEPACKFILES folder (If it exists)
3. Delete the actual file
4. WFP will detect the change and will try to restore it by requesting for the Install-CD (Press Cancel)
 
 Note WFP isn't active when booted to safe mode or [recovery console](/article/winnt-recovery-console.html). When the WFP isn't active it doesn't detect when files are deleted/replaced. Therefore it is possible to replace/delete files in this state without WFP interfering. When the WFP is activated again then it will not detect the new file, since it will only activate on file change or if requesting a [full scan](/article/winnt-sfc.html).  
  
 Note that some AntiVira software uses a large amount of resource on monitoring the DLLCACHE folder, and it can be a good idea to exclude the DLLCACHE folder so it is not scanned.  
- **You can momentarily disable it through the registry by changing this DWORD :**
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\ CurrentVersion \\Winlogon\]  
  >  SFCDisable=1 (Default=0)
  
   Note these other HEX values are possible :  
   0 - Enabled  
   1 - Disable will prompt at next boot to enable  
   2 - Disabled for next boot only, no prompt for enable  
   4 - Enabled with popups disabled(Server)  
   0xffffff9d - Disable completely (Only Works with Win2k SP1 and below)
- **You can increase it's scans by changing this DWORD:**
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\ CurrentVersion \\Winlogon\]  
  >  SFCScan=1 (Default=0)
  
   Note these values are possible :  
   0 - Do not scan at every boot  
   1 - Scan protected files at every boot  
   2 - Scan protected files once
- **You can increase/limit the space used for the backup, through this DWORD:**
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\ CurrentVersion \\Winlogon\]  
  >  SFCQuota=0xffffffff
  
   Note that Prof. uses 150 MB (0x32), Server uses 300 MB (0x12c), Advanced Server uses all the space it can find until 150 MB free (0xffffffff)
- **You can choose where to backup the files, by changing this STRING:**
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\ CurrentVersion \\Winlogon\]  
  >  SFCDllCacheDir="%SystemRoot%\\System32"
- **You can choose to display System File checker progress-meter by changing this DWORD:**
  > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT\\ CurrentVersion \\Winlogon\]  
  >  SFCShowProgress=1 (Default - 0 (Disabled))
 
 More Info [MS KB222473](http://support.microsoft.com/kb/222473 "Registry Settings for Windows File Protection (MS KB222473) [Q222473]")  
 More Info [MS KB222193](http://support.microsoft.com/kb/222193 "Description of the Windows 2000 Windows File Protection Feature (MS KB222193) [Q222193]")  
 More Info [MS KB271484](http://support.microsoft.com/kb/271484 "Files and Folders Are Added to Your System After Service Pack Is Installed [Q271484]")  
 More Info [MS KB290402](http://support.microsoft.com/kb/290402 "HOW TO: Remove the Service Pack Restore Files and Folders in Windows (MS KB290402) [Q290402]")  
  
 Credits [is-it-true.org](http://www.is-it-true.org/)