---
title: 'Load registry hive for offline registry editing'
date: '2003-02-28T01:19:35+01:00'
status: publish
permalink: /article/winnt-offline-registry-edit.html
author: Snakefoot
excerpt: 'The registry editor is capable of editing an offline registry hive.'
type: post
id: 254
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - regedit
    - registry
    - system-recovery
post_format: []
tags:
    - 'registry,regedit,system-recovery'
---
If needing to access the registry database on a system that is no longer bootable, then one should use [Windows PE or a Linux Live CD](/article/winnt-preinstalled-environment.html).  
  
 With REGEDT32 one can load and edit offline registry databases:

1. Start REGEDT32
2. Highlight the HKEY\_LOCAL\_MACHINE-window and select the root of the tree
3. In the menu select "Registry" -&gt; "Load Hive"
4. Select the wanted registry database file: 
  - \[HKEY\_LOCAL\_MACHINE \\SYSTEM\] (%windir%/system32/config/system)
  - \[HKEY\_LOCAL\_MACHINE \\SOFTWARE\] (%windir%/system32/config/software)
  - \[HKEY\_USERS \\.Default\] (%windir%/system32/config/default)
  - \[HKEY\_CURRENT\_USER\] (%userprofile%/ntuser.dat)
5. When prompted for a name give it whatever name you like (etc. test1). The name will be used to create a new node in the tree so one can browse the offline registry.
6. Go to the newly created node and edit whatever you like (The changes are written immediately to the offline registry database). One can import/export between the newly created node and the current registry just browse between the corresponding keys. 
  - To export a single key(with subkeys) into a file: Select the wanted key and in the menu "Registry" use "Save Key".
  - To import a single key or tree from a file: Select the location where the key should be imported and in the menu "Registry" use "Restore". Be very careful to select the same location from which is was exported as the restore will erase everything below the import location and replace with the contents of the file.
7. When finished editing select the newly created node and in the menu select "Registry" -&gt; "Unload Hive"
 
 This gives some possibilities:
- Load another users HKEY\_CURRENT\_USER (ntuser.dat) and change the users settings without logging in with the user.
- Load an offline registry database and extract settings to import in the current registry database.
- Load an offline \[HKEY\_USERS \\.Default\] and change the login screensaver to [Reset Administrator Password](/article/winnt-reset-password.html)
- Load and edit the registry database on a parallel installation without needing to boot it first.
- Repair the registry without using a parallel installation: 
  - [Use the Recovery Console to recover from faulty registry](/article/winnt-recovery-console-registry-restore.html)
  - Boot Windows in safemode using the restored registry database
  - Start REGEDT32 and load the faulty registry and edit away the faults
  - Boot into the Recovery Console again to exchange the now hopefully fixed registry database back (winnt/system32/config)
  - Boot Windows and it will now be using the fixed registry database
 
 Note WinXP has a new feature called [Registry Repair and Recovery (MS KB815011)](http://support.microsoft.com/kb/815011 "Cannot Disable the Registry Repair and Recovery Feature in Windows XP SP1 [Q815011]") and it is usually activated when starting WinXP. But it is also activated when loading an offline hive, which can have the undesired effect that the loaded hive is modifying behind your back. One can disable this feature in WinXP SP1 in case one is afraid that the "Repair" feature will do more harm than good:
> \[HKEY\_LOCAL\_MACHINE\\ System \\CurrentControlSet \\Control \\Session Manager \\Configuration Manager\]  
>  SelfHealingEnabled = 0

 More Info [MS KB146050](http://support.microsoft.com/kb/146050 "Modifying Ntuser.dat Hive So New Users Get Defined Settings [Q146050]")  
  
 Credits [jsifaq.com](http://jsifaq.com/)