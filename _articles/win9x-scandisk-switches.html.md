---
title: 'Scandisk command line switches'
date: '2000-01-01T23:24:34+01:00'
permalink: /article/win9x-scandisk-switches.html
author: Snakefoot
excerpt: 'List of the available command line switches for scandisk.'
type: post
id: 128
categories:
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
    - ms-dos_tips
tags:
    - command-line-switches
    - scandisk
---
If you want to schedule the checking of your HDD, then use these command line switches:  
  
 Scandisk (Dos):

- **drive:** - Drive letter of disk you want to scan.
- **/A or /ALL** - Scans all local, non-removable hard drives.
- **/Autofix** - Fixes damages without prompting.
- **/Checkonly** - Tests for errors but doesn't make any changes.
- **/Custom** - Configures and runs Scandisk according to the Scandisk.ini file settings.
- **/Nosave** - With /autofix, deletes lost clusters rather than saving as files.
- **/Nosummary** - With /checkonly or /autofix, it skips summary screen.
- **/O** - Undocumented, deletes all long file entries only leaving the 8.3 filename (Dangerous)
- **/Surface** - Performs a surface scan after other checks.
- **/mono** - Configures Scandisk for use with monochrome display.
 
 Scandskw (Windows 9x): - **drive:** - Drive letter of disk you want to scan
- **/Allfixeddisks** - Scan all local, non-removable hard drives
- **/Noninteractive** - Runs scandisk without requiring user input
- **/Preview** - Preview tests for errors but doesn't make any changes
- **/Oldfs** - Undocumented, deletes all long file entries only leaving the 8.3 filename (Dangerous)
- **/Silent** - Doesn't display summary screen
- **/Sageset:x** - Used to create a profile (x is a number from 0-65535)
- **/Sagerun:x** - Used to execute a created profile (x is a number from 0-65535)
 
 More Info <a href="https://www.bing.com/search?q=KB%20126280%20Q126280" rel="nofollow" title="Windows 95 ScanDisk (SCANDSKW) Exit Codes [Q126280]">MS KB126280</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20127055%20Q127055" rel="nofollow" title="How to Cause ScanDisk for Windows to Retest Bad Clusters [Q127055]">MS KB127055</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20186365%20Q186365" rel="nofollow" title="Description of ScanDisk for Windows (Scandskw.exe) in Windows 98/Me [Q186365]">MS KB186365</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20199557%20Q199557" rel="nofollow" title="Command-Line Parameters for the Scandisk Tool [Q199557]">MS KB199557</a>  
  
 Credits [Serenity](http://www.mvps.org/serenitymacros/)