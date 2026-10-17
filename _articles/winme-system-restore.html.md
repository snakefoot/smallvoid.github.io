---
title: 'Using the System Restore in Windows Me'
date: '2003-06-21T19:46:26+02:00'
permalink: /article/winme-system-restore.html
author: Snakefoot
excerpt: 'Details of how System Restore works in Windows Me and how to configure it.'
type: post
id: 107
categories:
    - windows-me_troubleshoot
tags:
    - restore-point
    - system-file-protection
    - system-restore
---
System Restore makes it possible to go back to a previous known good configuration (Before one self or an application screwed up the system). System Restore saves the the current Windows configuration in a restore point, and if any accident should occur, then one can return to the saved restore point. Restore Points are automatically created regularly at certain events, so a recent Restore Point is always available.  
  
 The files included/excluded in a Restore Point are specified in the textfile:

> %Windir%\\System\\Restore\\Filelist.xml

 Any changed file that are included in the Filelist.xml will be copied to C:\\\_Restore (CPY Files). This behavior can lead to heavy load on the HDD if a file is frequently modified. To avoid this one can [Exclude the file from system restore](/article/winme-exclude-system-restore.html) or just disable System Restore completely.  
  
 The System Restore utility can be used to create restore points manually or go back to a previous restore point. To access this utility press **Start**-button -&gt; **Programs** -&gt; **System Tools** -&gt; **System Restore**. One can also start the tool from the command line:
 > %Windir%\\System\\Restore\\Rstrui.exe

 Note when restoring a restore point it will remove files with certain extensions (.exe etc.), which have appeared since the restore point. Unless they were placed in a folder not monitored by System File Protection like My Documents. (If one discovers that some wanted files was deleted during a restore, then it is still possible to undo the restore with the utility)  
  
 Note one can configure how much space the C:\\\_Restore folder is allowed to use:
- Open **Control Panel** and select **System**
- Select the **Performance**-fan. Press the **File System**-button. Select the **Hard Disk**-tab
- Adjust **System Restore disk space use** to the preferred size
 
 Note <a href="https://www.bing.com/search?q=KB+264887+Q264887" title="How to Enable and Disable System Restore [Q264887]") will cause all system restore points to be deleted. Though it seems to be a necessary action to reinitialize System Restore in case one [moves the My Documents folder](http://support.microsoft.com/kb/253682 "How to Change the Default Location of the My Documents Folder [Q253682]" rel="nofollow">disabling system restore</a> or if a virus have infected the saved restore points.  
  
 Note System Restore is not a vital part of Windows Me and if using applications, which performs many file operations like using a database or compiling, then one should consider disabling System Restore for good.  
  
 Note that some AntiVira software uses a large amount of resource on monitoring the ?:\\\_Restore folder. It can be a good idea to exclude the folders so they are not scanned.  
  
 Note one can only use restore points inside Windows, if in the situation where Windows won't even start in safe mode, then one have to use the [Scanreg](/article/win9x-registry-checker.html) tool to restore a previous version of the registry.  
  
 More Info <a href="https://www.bing.com/search?q=KB+261716+Q261716" rel="nofollow" title="System Restore Removes Files During a Restore Procedure [Q261716]">MS KB261716</a>  
 More Info <a href="https://www.bing.com/search?q=KB+263455+Q263455" rel="nofollow" title="Antivirus Tools Cannot Clean Infected Files in the _Restore Folder [Q263455]">MS KB263455</a>  
 More Info <a href="https://www.bing.com/search?q=KB+264152+Q264152" rel="nofollow" title="Deleting the _Restore Folder from a Non-Windows Me Partition Resets the Data Store [Q264152]">MS KB264152</a>  
 More Info <a href="https://www.bing.com/search?q=KB+267176+Q267176" rel="nofollow" title="Unable to Access the System Restore Buttons If Screen Resolution Is 800x600 or Less [Q267176]">MS KB267176</a>  
 More Info <a href="https://www.bing.com/search?q=KB+267698+Q267698" rel="nofollow" title="Computer May Not Start Properly After You Use a System Restore Point [Q267698]">MS KB267698</a>  
 More Info <a href="https://www.bing.com/search?q=KB+267951+Q267951" rel="nofollow" title="Description of the System Restore Utility in Windows Millennium Edition [Q267951]">MS KB267951</a>  
 More Info <a href="https://www.bing.com/search?q=KB+279736+Q279736" rel="nofollow" title="How to Start the System Restore Tool from a Command Prompt [Q279736]">MS KB279736</a>  
 More Info <a href="https://www.bing.com/search?q=KB+303354+Q303354" rel="nofollow" title="Error Message: System Restore Was Unable to Create a Restore Point [Q303354]">MS KB303354</a>  
 More Info [MSDN: Windows System Restore](http://msdn.microsoft.com/library/en-us/dnsetup/html/winmesr.asp)  