---
title: 'Extend Windows Vista activation period'
date: '2007-07-02T07:45:10+02:00'
status: publish
permalink: /article/vista-extend-activation.html
author: Snakefoot
excerpt: 'Windows Vista Software Licensing Manager makes it possible to extend the period before activation is needed.'
type: post
id: 650
category:
    - Troubleshoot
tag:
    - activation-period
    - software-license-manager
    - windows-product-activation
post_format: []
tags:
    - 'activation-period,windows-product-activation,software-license-manager'
---
Windows Vista has like Windows XP a 30 day activation period, and if not able to perform the Windows Product Activation within the period then it is crippled to only boot in safemode.  
  
 Windows Vista has a Software Licensing Manager, which can be used to extend the activation period with another 30 days (Must be executed from an [Elevated Command Prompt](/article/winnt-user-account-protection.html#ELEVATED) with Administrator privileges):

> cscript slmgr.vbs -rearm

 This can also be done with this command:
 > rundll32 slc.dll,SLReArmWindows

 The above commands can be executed 3 times (in total 120 days), and then it will not extend the activation period any longer. Running this command from a command-prompt will show the new expiration date of the activation period:
 > cscript slmgr.vbs -xpr

 Note it is possible to perform the rearm indefinitely by setting this registry key before running the rearm command:
 > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows NT \\CurrentVersion \\SL\]  
 >  SkipRearm = 1

 Credits [WindowsSecrets.com](http://windowssecrets.com/)