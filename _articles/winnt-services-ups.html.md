---
title: 'Uninterruptible Power Supply (UPS)'
date: '2000-06-06T19:59:11+02:00'
permalink: /article/winnt-services-ups.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Uninterruptible Power Supply service.'
type: post
id: 609
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
tags:
    - power-management
    - uninterruptible-power-supply
---
##### Description:

 Is used to provide support for an UPS (Uninteruptable Power Supply) if such exists. Though many new UPSs doesn't use this UPS service but provide their own drivers for controlling the behavior of the USP.  
  
 The UPS can be configured in the Power Settings-Applet in the Control Panel.  
  
 Note when the UPS service is running it might claim control of serial port COM1/COM2 so no other program can use it.  
  
 More Info <a href="https://www.bing.com/search?q=KB+170817+Q170817" rel="nofollow" title="Windows NT Causes APC Smart UPS Battery to Discharge [Q170817]">MS KB170817</a>  
 More Info <a href="https://www.bing.com/search?q=KB+310437+Q310437" rel="nofollow" title="Cannot Start the UPS Service [Q310437]">MS KB310437</a>  
  
##### Recommended State:

- Manual.

##### Default State:

- Manual.

##### Process Name:

- ups.exe (UPS)

##### Supports:

- None

##### Depends:

- None