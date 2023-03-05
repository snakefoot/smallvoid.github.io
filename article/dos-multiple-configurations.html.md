---
title: 'Use multiple DOS startup configurations'
date: '2000-01-01T23:44:41+01:00'
status: publish
permalink: /article/dos-multiple-configurations.html
author: Snakefoot
excerpt: 'How to configure the config.sys and autoexec.bat to use multiple startup configurations.'
type: post
id: 56
category:
    - Tips
tag:
    - autoexec-bat
    - boot-time
    - config-sys
    - menu-config
post_format: []
tags:
    - 'menu-config,autoexec-bat,config-sys,boot-time'
---
MS DOS 6.0 introduced the ability to specify multiple configurations in the Config.sys and Autoexec.bat. This feature can be used for different situations:

- Dual boot situation with the option to either boot in DOS with all device drivers loaded (CDROM etc.), or to boot in Windows 95 where it should not load any DOS device drivers.
- Different memory configurations whether to have lots of conventional memory or [expanded memory](/article/expanded-memory-ems-extended-memory-xms.html).
- Starting DOS with or without support for network or CDROM drives.
 
 This is a simple Config.sys, which tries to outline the basics of multiple configurations with the use of **MENU** and **MENUITEM**:
> \[MENU\]  
>  REM Define an item in the menu, first identifier and then what  
>  REM is written in the menu  
>  MENUITEM=DOS, DOS with CD-ROM  
>  MENUITEM=WIN, Windows  
>   
>  REM The commands at COMMON is executed no matter what is chosen  
>  REM in the MENU  
>  \[COMMON\]  
>  DOS=HIGH,UMB  
>   
>  REM For each menu item there can be defined a configuration  
>  \[DOS\]  
>  DEVICE=C:\\DOS\\HIMEM.SYS /TESTMEM:OFF  
>  DEVICE=C:\\DOS\\EMM386.EXE NOEMS  
>  DEVICE=C:\\CDROM\\DRIVER.SYS /D:CD1  
>   
>  \[WIN\]  
>  DEVICE=C:\\DOS\\HIMEM.SYS /TESTMEM:OFF

 This is a simple Autoexec.bat, where the **MENUITEM** is translated into the label **CONFIG**:
> @ECHO OFF  
>  PROMPT=$P$G  
>  SET DIRCMD=/A/OGN/P  
>   
>  REM Uses the identifier from CONFIG.SYS to goto a label  
>  GOTO %CONFIG%  
>   
>  REM This is the label for the identifier DOS  
>  :DOS  
>  LH C:\\DOS\\MSCDEX.EXE /D:CD1  
>  LH C:\\DOS\\SMARTDRV.EXE 2048  
>   
>  REM The GOTO EXIT is required so it won't continue into  
>  REM the WIN configuration  
>  GOTO EXIT  
>   
>  REM This is the label for the identifier WIN  
>  :WIN  
>   
>  REM The ECHO command writes a message on the DOS screen  
>  ECHO Starting Windows...  
>   
>  C:\\WINDOWS\\WIN  
>   
>  :EXIT

 It is possible to extend menu-system in the config.sys with **SUBMENU**, which enables sub-menus. One can also use **MENUDEFAULT** to specify the default menu item and how long it should wait before it picks the default. > \[MENU\]  
>  MENUITEM=DOS, DOS with CD-ROM  
>  MENUITEM=WIN, Windows  
>   
>  REM By using SUBMENU you will creating an extra menu(TEST)  
>  SUBMENU=TEST, Testing  
>   
>  REM Using MENUDEAFAULT makes it possible to choose a certain  
>  REM item(WIN) and if it's set also select that item after a certain  
>  REM time(20 secs)  
>  MENUDEFAULT=WIN, 20  
>   
>  REM Here is the SUBMENU it can also include other SUBMENUs  
>  \[TEST\]  
>  MENUITEM=TEST1, Testing 1

 To read more about multi-configurations menus execute the following command:
 
 > help multi-config

 More Info [MS KB91202](http://support.microsoft.com/kb/91202 "Multiple Configuration Menu Is Not Displayed [Q91202]")