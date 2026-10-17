---
title: 'Outlook safemode command line switch'
date: '2004-11-26T18:49:15+01:00'
permalink: /article/outlook-safemode.html
author: Snakefoot
excerpt: 'Starting Outlook in safemode can be useful when troubleshooting Outlook.'
type: post
id: 336
categories:
    - email-reader_outlook
tags:
    - command-line-switches
    - safemode
---
When Outlook fails to start because it crashes or stops/freezes at the splash screen, then one can try to run it in safemode where the following is disabled:

- Extensions/[Addons](/article/outlook-advanced-security.html)
- Preview pane
- Toolbar customization
 
 To start in safemode use the following command line switch:
 
> Outlook.exe /safe  
>   
>  More info <a href="https://www.bing.com/search?q=KB%20182112%20Q182112" rel="nofollow" title="OL98: Additional Command-Line Switches [Q182112]">MS KB182112</a>  
>  More info <a href="https://www.bing.com/search?q=KB%20197180%20Q197180" rel="nofollow" title="OL2000: Additional Command-Line Switches [Q197180]">MS KB197180</a>  
>  More info <a href="https://www.bing.com/search?q=KB%20296192%20Q296192" rel="nofollow" title="OL2002: Additional Command-Line Switches [Q296192]">MS KB296192</a>

 Note if Outlook has a slow startup or performs slowly (but can start), then one can try to activate the builtin repair tool. It can be found under **Tools** and **Detect &amp; Repair**. Also consider to check if having installed Outlook addins that are causing problems (Antivirus addins can also malfunction). If loading local mail archives that are broken can also cause bad performance. More Info <a href="https://www.bing.com/search?q=KB%20291957%20Q291957" rel="nofollow" title="OL2000: How to Force the Detect and Repair Tool to Run in Outlook 2000">MS KB291957</a>  
  
 Note if the safemode option solves the problem with actually starting Outlook, then renaming the following files should enable starting Outlook without safemode (Search the computer for the files): 
- Views.dat (Stores views associated with the Integrated File Management component)
  > Outlook.exe /CleanViews
- Outcmd.dat (Stores menu style settings)
- Extend.dat (Cache for extension registry entries - More info <a href="https://www.bing.com/search?q=KB%20286408%20Q286408" rel="nofollow" title="Description of Outlook and Exchange client extensions [Q286408]">MS KB286408</a>)
- Frmcache.dat (Cache for default and custom forms - More info <a href="https://www.bing.com/search?q=KB%20290806%20Q290806" rel="nofollow" title="Description of Outlook 2002 forms cache [Q290806]">MS KB290806</a>)
- Usrclass.dat
 
 More info <a href="https://www.bing.com/search?q=KB%20195754%20Q195754" rel="nofollow" title="OL2000: How to Clear the Outlook Forms Cache [Q195754]">MS KB195754</a>  
 More info <a href="https://www.bing.com/search?q=KB%20232314%20Q232314" rel="nofollow" title="OL2000: How to Troubleshoot the Outlook Forms Cache [Q232314]">MS KB232314</a>  
 More info <a href="https://www.bing.com/search?q=KB%20241817%20Q241817" rel="nofollow" title="You receive error messages when you start Outlook and send mails in Outlook 2000 [Q241817]">MS KB241817</a>  
 More info <a href="https://www.bing.com/search?q=KB%20249767%20Q249767" rel="nofollow" title="Outlook 2000 performs slowly or stops responding [Q249767]">MS KB249767</a>  
 More info <a href="https://www.bing.com/search?q=KB%20305928%20Q305928" rel="nofollow" title="Outlook 2000 stops responding at the startup splash screen [Q305928]">MS KB305928</a>  
 More info <a href="https://www.bing.com/search?q=KB%20320835%20Q320835" rel="nofollow" title="OL2002: You Receive an Error Message When You Try to Open a Custom Form in Outlook [Q320835]">MS KB320835</a>  
 More info <a href="https://www.bing.com/search?q=KB%20839804%20Q839804" rel="nofollow" title="How to use the Outlook 2003 forms cache and to troubleshoot forms cache problems [Q839804]">MS KB839804</a>  
  
 Credits [OneComputerGuy.com](http://onecomputerguy.com/)