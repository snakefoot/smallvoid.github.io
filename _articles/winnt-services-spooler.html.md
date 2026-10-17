---
title: 'Print Spooler'
date: '2000-06-06T16:15:49+02:00'
permalink: /article/winnt-services-spooler.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Print Spooler service.'
type: post
id: 573
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
    - windows-8-win8_services-guide
tags:
    - print-spooler
    - printer
---
##### Description:

 Is used to print files local or from remote, and to store/send print job to available print devices.  
 The Printer Spooler also allows one to pool together several printers attached to the machine and make them act like one printer.  
  
 Related [How to configure the Print Spooler service](/article/winnt-printer-spooler-config.html)  
 Related [Reinstalling printer drivers](/article/winnt-reinstall-printer-driver.html)  
 Related [Change printer spool directory](/article/winnt-print-spool-folder.html)  
  
 More Info <a href="https://www.bing.com/search?q=KB+161734+Q161734" rel="nofollow" title="Windows NT and Windows 2000 Print Browsing Architecture [Q161734]">MS KB161734</a>  
 More Info <a href="https://www.bing.com/search?q=KB+278455+Q278455" rel="nofollow" title="How to Set Up a Clustered Print Server [Q278455]">MS KB278455</a>  
 More Info <a href="https://www.bing.com/search?q=KB+300392+Q300392" rel="nofollow" title="HOW TO: Install and Configure a File and Print Server in Windows 2000 [Q300392]">MS KB300392</a>  
 More Info <a href="https://www.bing.com/search?q=KB+305402+Q305402" rel="nofollow" title="HOW TO: Change Printing Preferences on Print Server for All Connected Users [Q305402]">MS KB305402</a>  
 More Info <a href="https://www.bing.com/search?q=KB+313058+Q313058" rel="nofollow" title="How To Configure Internet Printing in Windows 2000 [Q313058]">MS KB313058</a>  
 More Info <a href="https://www.bing.com/search?q=KB+313725+Q313725" rel="nofollow" title="HOW TO: Configure Printer Settings in Windows 2000 Server [Q313725]">MS KB313725</a>  
 More Info <a href="https://www.bing.com/search?q=KB+323428+Q323428" rel="nofollow" title="HOW TO: Configure Internet Printing in Windows Server 2003 [Q323428]">MS KB323428</a>  
 More Info <a href="https://www.bing.com/search?q=KB+324078+Q324078" rel="nofollow" title="HOW TO: Install and Configure Print Services for UNIX [Q324078]">MS KB324078</a>  
 More Info <a href="https://www.bing.com/search?q=KB+325860+Q325860" rel="nofollow" title="HOW TO: Install and Configure a File and Print Server in Windows Server 2003 [Q325860]">MS KB325860</a>  
  
##### Recommended State:

- Disabled, if not having a printer.
- Automatic, if using a local or networked printer.

##### Default State:

- Automatic

##### Process Name:

- spoolsv.exe (Spooler)

##### Supports:

- [FAX Service](/article/winnt-services-fax.html) (Win7\\Vista\\WinXP\\Win2k\\WinNT4 only)

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)