---
title: 'Configure Windows 9x startup with Msdos.sys'
date: '2000-01-01T03:00:28+01:00'
status: publish
permalink: /article/win9x-msdos-sys.html
author: Snakefoot
excerpt: 'List of the different settings available in Msdos.sys.'
type: post
id: 136
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - bootmenu
    - msdos-sys
post_format: []
tags:
    - 'msdos-sys,bootmenu'
---
The Msdos.sys file is located in the root of the system partition (Usually C:), and contains settings that control the startup of Windows 9x. The Msdos.sys is a standard text-file, which can be edited using Notepad.  
  
 The MsDos.sys contains two sections:

- **\[Paths\]** - Specifies the location of the Windows installation.
- **\[Options\]** - Specifies the settings used at Windows startup.
 
 Some of the more useful settings available in the **\[options\]**-section: <table border="1"><tr><th>Setting</th><th>Description</th></tr><tr><td>AutoScan = 2</td><td>Run scandisk at startup after Windows crash (0 = No, 1 = Prompt, 2 = Scan)</td></tr><tr><td>BootDelay = 0</td><td>How many seconds one have to press F5/F8 to break startup</td></tr><tr><td>BootGUI = 1</td><td>Launch Windows after running Autoexec.bat</td></tr><tr><td>BootKeys = 1</td><td>Enable [startup keyboard keys (F5/F8)](/article/bypass-step-through-config-sys.html)</td></tr><tr><td>BootMenu = 1</td><td>Show boot menu by default, like if the F8 key was pressed</td></tr><tr><td>BootMenuDelay = 3</td><td>How many seconds it should show the boot menu before continuing</td></tr><tr><td>BootMulti = 0</td><td>Allows booting to the previous operating system Windows by pressing F8 at startup</td></tr><tr><td>DblSpace = 0</td><td>Load double space drivers</td></tr><tr><td>DrvSpace = 0</td><td>Load drive space drivers</td></tr><tr><td>DoubleBuffer = 0</td><td>Enable double buffering for SCSI devices</td></tr><tr><td>Loadtop = 1</td><td>Load Command.com in [upper memory](/article/upper-memory-block-umb.html)</td></tr><tr><td>Logo = 1</td><td>Show Windows logo while booting</td></tr><tr><td>Network = 1</td><td>Enable network support in [safemode](http://support.microsoft.com/kb/122051 "How Windows 95 Performs a Safe-Mode Start [Q122051]")</td></tr></table>

 More Info [MS KB118579](http://support.microsoft.com/kb/118579 "Contents of the Windows Msdos.sys File [Q118579]")