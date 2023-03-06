---
title: 'Outlook safemode command line switch'
date: '2004-11-26T18:49:15+01:00'
status: publish
permalink: /article/outlook-safemode.html
author: Snakefoot
excerpt: 'Starting Outlook in safemode can be useful when troubleshooting Outlook.'
type: post
id: 336
category:
    - Outlook
tag:
    - command-line-switches
    - safemode
post_format: []
tags:
    - 'safemode,command-line-switches'
---
When Outlook fails to start because it crashes or stops/freezes at the splash screen, then one can try to run it in safemode where the following is disabled:

- Extensions/[Addons](/article/outlook-advanced-security.html)
- Preview pane
- Toolbar customization
 
 To start in safemode use the following command line switch:
 
> Outlook.exe /safe  
>   
>  More info [MS KB182112](http://support.microsoft.com/kb/182112 "OL98: Additional Command-Line Switches [Q182112]")  
>  More info [MS KB197180](http://support.microsoft.com/kb/197180 "OL2000: Additional Command-Line Switches [Q197180]")  
>  More info [MS KB296192](http://support.microsoft.com/kb/296192 "OL2002: Additional Command-Line Switches [Q296192]")

 Note if Outlook has a slow startup or performs slowly (but can start), then one can try to activate the builtin repair tool. It can be found under **Tools** and **Detect &amp; Repair**. Also consider to check if having installed Outlook addins that are causing problems (Antivirus addins can also malfunction). If loading local mail archives that are broken can also cause bad performance. More Info [MS KB291957](http://support.microsoft.com/kb/291957 "OL2000: How to Force the Detect and Repair Tool to Run in Outlook 2000")  
  
 Note if the safemode option solves the problem with actually starting Outlook, then renaming the following files should enable starting Outlook without safemode (Search the computer for the files): 
- Views.dat (Stores views associated with the Integrated File Management component)
  > Outlook.exe /CleanViews
- Outcmd.dat (Stores menu style settings)
- Extend.dat (Cache for extension registry entries - More info [MS KB286408](http://support.microsoft.com/kb/286408 "Description of Outlook and Exchange client extensions [Q286408]"))
- Frmcache.dat (Cache for default and custom forms - More info [MS KB290806](http://support.microsoft.com/kb/290806 "Description of Outlook 2002 forms cache [Q290806]"))
- Usrclass.dat
 
 More info [MS KB195754](http://support.microsoft.com/kb/195754 "OL2000: How to Clear the Outlook Forms Cache [Q195754]")  
 More info [MS KB232314](http://support.microsoft.com/kb/232314 "OL2000: How to Troubleshoot the Outlook Forms Cache [Q232314]")  
 More info [MS KB241817](http://support.microsoft.com/kb/241817 "You receive error messages when you start Outlook and send mails in Outlook 2000 [Q241817]")  
 More info [MS KB249767](http://support.microsoft.com/kb/249767 "Outlook 2000 performs slowly or stops responding [Q249767]")  
 More info [MS KB305928](http://support.microsoft.com/kb/305928 "Outlook 2000 stops responding at the startup splash screen [Q305928]")  
 More info [MS KB320835](http://support.microsoft.com/kb/320835 "OL2002: You Receive an Error Message When You Try to Open a Custom Form in Outlook [Q320835]")  
 More info [MS KB839804](http://support.microsoft.com/kb/839804 "How to use the Outlook 2003 forms cache and to troubleshoot forms cache problems [Q839804]")  
  
 Credits [OneComputerGuy.com](http://onecomputerguy.com/)