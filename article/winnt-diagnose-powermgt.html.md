---
title: 'Troubleshoot problems with entering sleep mode'
date: '2009-10-29T00:44:19+01:00'
status: publish
permalink: /article/winnt-diagnose-powermgt.html
author: Snakefoot
excerpt: 'Diagnose what is preventing your computer from entering sleep mode, or wakes it prematurely.'
type: post
id: 821
category:
    - Tips
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - power-management
post_format: []
tags:
    - power-management
---
Power Management have been around since the first laptop was released to the main stream. For some strange reason power management have always had a lot of child diceases (crashes, slow-downs or just not saving power).  
  
 There are different commands available to diagnose power management issues:

- **What devices can wake the computer from sleep mode:**
  > powercfg -devicequery wake\_from\_any
- **What devices can wake the computer from standby:**
  > powercfg -devicequery wake\_armed
- **Disable a device ability to wake the computer:**
  > powercfg -devicedisablewake "device name"
- **Make a device able to wake the computer:**
  > powercfg -deviceenablewake "device name"

##### New Vista Commands

- **What device caused computer to wake from sleep mode:**
  > powercfg -lastwake
 
 More Info [MS Technet - Powercfg Command-Line Options](http://technet.microsoft.com/en-us/library/cc748940(WS.10).aspx)
 
##### New Windows 7 Commands

 Windows 7 introduces some new commands, and if installing Win7 on a laptop, then one should try out the following commands:
- **Analyze the power comsumption of the computer, and lists devices with issues:**
  > powercfg -energy
- **Diagnose why the computer is not able to enter sleep mode:**
  > powercfg -requests
 
 More Info [MS KB976877](http://support.microsoft.com/kb/976877 "Windows 7 does not go to sleep")  
  
 Credits [The Old New Thing](http://blogs.msdn.com/oldnewthing/archive/2009/10/26/9912711.aspx)