---
title: 'Mapping network printer to LTP1'
date: '2009-10-15T21:50:14+02:00'
permalink: /article/winnt-map-printer.html
author: Snakefoot
excerpt: 'How to solve access denied error when trying to map network printer to LPT1'
type: post
id: 818
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-xp_troubleshoot
tags:
    - dos-emulator
    - LPT1
    - printer
    - PRN
---
When wanting to print from old DOS programs, then one is required to attach a printer to LPT1 or LPT2.  
  
 It is possible to map a network printer to LPT1 with this command:

> net use lpt1: \\\\computer\_name\\printer

 Note if the mapping fails because of "Access Denied", then it can be caused by different things:
 - The network permissions for the printer share, doesn't allow the user to access the printer.
 - The user is not allowed to remap the LPT1 port, this happens if the LPT1 is already mapped to a local port. The solution is to disable the LPT1 port on the motherboard BIOS.
 
 Note the method of mapping a network printer to LPT1 can also be used to map an USB printer. First share the printer, and then map the printer to LPT1.  
  
 Note if the DOS program is able to print, but nothing comes out of the printer, then you might have to change the printer properties to TEXT mode.  
  
 More Info <a href="https://www.bing.com/search?q=KB+163551+Q163551" rel="nofollow" title="Troubleshooting Printing Problems in Windows 2000 and Windows NT 4.0 [Q163551]">MS KB163551</a>  
  
 Credits [GeeksWithBlogs.net](http://geekswithblogs.net/dtotzke/articles/26204.aspx)