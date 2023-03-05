---
title: 'Using file compare to see changes made to the registry'
date: '2001-01-01T12:48:29+01:00'
status: publish
permalink: /article/windows-file-compare-registry.html
author: Snakefoot
excerpt: 'How to see the registry changes of a certain action by using the file compare utility.'
type: post
id: 242
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - file-compare
    - process-monitor
    - regedit
    - registry
post_format: []
tags:
    - 'regedit,registry,file-compare,process-monitor'
---
If wanting to see what registry entries are modified when performing a certain action, then one can use the Registry Editor to export the Windows registry before before performing the action and export after having performed the action.  
  
 Then one can use the file compare utility to see what changes have been made:

> FC before.reg after.reg &gt; diff.txt

 Note when exporting the registry hives in Windows 2000,XP,2003 then they are exported as unicode (Windows Registry Editor Version 5.00). To perform a file compare on two unicode files:
 > FC before.reg after.reg /U &gt; diff.txt

 Note instead of exporting the registry, then one could also use Process Monitor by [SysInternals.com](http://www.sysinternals.com/) to see the registry changes made by an application.