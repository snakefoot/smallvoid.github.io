---
title: 'Uninterruptible Power Supply (UPS)'
date: '2000-06-06T19:59:11+02:00'
status: publish
permalink: /article/winnt-services-ups.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Uninterruptible Power Supply service.'
type: post
id: 609
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - power-management
    - uninterruptible-power-supply
post_format: []
tags:
    - 'uninterruptible-power-supply,power-management'
---
##### Description:

 Is used to provide support for an UPS (Uninteruptable Power Supply) if such exists. Though many new UPSs doesn't use this UPS service but provide their own drivers for controlling the behavior of the USP.  
  
 The UPS can be configured in the Power Settings-Applet in the Control Panel.  
  
 Note when the UPS service is running it might claim control of serial port COM1/COM2 so no other program can use it.  
  
 More Info [MS KB170817](http://support.microsoft.com/kb/170817 "Windows NT Causes APC Smart UPS Battery to Discharge [Q170817]")  
 More Info [MS KB310437](http://support.microsoft.com/kb/310437 "Cannot Start the UPS Service [Q310437]")  
  
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