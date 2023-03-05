---
title: 'Mapping network printer to LTP1'
date: '2009-10-15T21:50:14+02:00'
status: publish
permalink: /article/winnt-map-printer.html
author: Snakefoot
excerpt: 'How to solve access denied error when trying to map network printer to LPT1'
type: post
id: 818
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - dos-emulator
    - LPT1
    - printer
    - PRN
post_format: []
tags:
    - 'printer,LPT1,dos-emulator,PRN'
---
When wanting to print from old DOS programs, then one is required to attach a printer to LPT1 or LPT2.  
  
 It is possible to map a network printer to LPT1 with this command:

> net use lpt1: \\\\computer\_name\\printer

 Note if the mapping fails because of "Access Denied", then it can be caused by different things:
 - The network permissions for the printer share, doesn't allow the user to access the printer.
 - The user is not allowed to remap the LPT1 port, this happens if the LPT1 is already mapped to a local port. The solution is to disable the LPT1 port on the motherboard BIOS.
 
 Note the method of mapping a network printer to LPT1 can also be used to map an USB printer. First share the printer, and then map the printer to LPT1.  
  
 Note if the DOS program is able to print, but nothing comes out of the printer, then you might have to change the printer properties to TEXT mode.  
  
 More Info [MS KB163551](http://support.microsoft.com/kb/163551 "Troubleshooting Printing Problems in Windows 2000 and Windows NT 4.0 [Q163551]")  
  
 Credits [GeeksWithBlogs.net](http://geekswithblogs.net/dtotzke/articles/26204.aspx)