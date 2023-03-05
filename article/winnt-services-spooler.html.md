---
title: 'Print Spooler'
date: '2000-06-06T16:15:49+02:00'
status: publish
permalink: /article/winnt-services-spooler.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Print Spooler service.'
type: post
id: 573
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - print-spooler
    - printer
post_format: []
tags:
    - 'printer,print-spooler'
---
##### Description:

 Is used to print files local or from remote, and to store/send print job to available print devices.  
 The Printer Spooler also allows one to pool together several printers attached to the machine and make them act like one printer.  
  
 Related [How to configure the Print Spooler service](/article/winnt-printer-spooler-config.html)  
 Related [Reinstalling printer drivers](/article/winnt-reinstall-printer-driver.html)  
 Related [Change printer spool directory](/article/winnt-print-spool-folder.html)  
  
 More Info [MS KB161734](http://support.microsoft.com/kb/161734 "Windows NT and Windows 2000 Print Browsing Architecture [Q161734]")  
 More Info [MS KB278455](http://support.microsoft.com/kb/278455 "How to Set Up a Clustered Print Server [Q278455]")  
 More Info [MS KB300392](http://support.microsoft.com/kb/300392 "HOW TO: Install and Configure a File and Print Server in Windows 2000 [Q300392]")  
 More Info [MS KB305402](http://support.microsoft.com/kb/305402 "HOW TO: Change Printing Preferences on Print Server for All Connected Users [Q305402]")  
 More Info [MS KB313058](http://support.microsoft.com/kb/313058 "How To Configure Internet Printing in Windows 2000 [Q313058]")  
 More Info [MS KB313725](http://support.microsoft.com/kb/313725 "HOW TO: Configure Printer Settings in Windows 2000 Server [Q313725]")  
 More Info [MS KB323428](http://support.microsoft.com/kb/323428 "HOW TO: Configure Internet Printing in Windows Server 2003 [Q323428]")  
 More Info [MS KB324078](http://support.microsoft.com/kb/324078 "HOW TO: Install and Configure Print Services for UNIX [Q324078]")  
 More Info [MS KB325860](http://support.microsoft.com/kb/325860 "HOW TO: Install and Configure a File and Print Server in Windows Server 2003 [Q325860]")  
  
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