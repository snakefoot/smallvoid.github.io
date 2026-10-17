---
title: 'Change location of the print spooler directory'
date: '2001-01-12T19:59:43+01:00'
permalink: /article/winnt-print-spool-folder.html
author: Snakefoot
excerpt: 'When printing a document, then the document is spooled into a temporary directory and then sent to the printer.'
type: post
id: 384
categories:
    - windows-2003_tips
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
tags:
    - free-disk-space
    - print-spooler
    - printer
---
There can be different reasons for changing the directory for the [Print Spooler Service](/article/winnt-services-spooler.html) on a print server:

- There is not enough room at the default location (%systemroot%\\system32\\spool\\printers) causing the large print jobs to fail
- There is a faster HDD available which can improve the performance of the printing
- There is a need to distribute the print jobs for different printers on different HDDs
 
 One can change the default location of the spool folder:
1. Control Panel -&gt; Printers
2. File-menu -&gt; Server Properties
3. Select the Advanced-tab and change the "Spool Folder"
 
 One can also change the default location in the registry:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Printers\]  
>  DefaultSpoolDirectory =

 One can change it for a specific printer:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Printers \\{Specific Printer Id}\]  
>  SpoolDirectory =

 Note if the contents of the spool directory becomes corrupted then it can keep the [Print Spooler Service](/article/winnt-services-spooler.html) from starting. Solve this by deleting/moving the contents of the printers spool directory. More Info <a href="https://www.bing.com/search?q=KB%20250038%20Q250038" rel="nofollow" title="Print Server Stops, Then Stops Again After You Stop and Restart Spooler Service [Q250038]">MS KB250038</a>  
  
 More Info <a href="https://www.bing.com/search?q=KB%20123747%20Q123747" rel="nofollow" title="Moving the Windows Default Paging and Spool File [Q123747]">MS KB123747</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20314105%20Q314105" rel="nofollow" title="How to Move the Windows Default Paging File and Print Spooler to a Different Hard Disk [Q314105]">MS KB314105</a>  