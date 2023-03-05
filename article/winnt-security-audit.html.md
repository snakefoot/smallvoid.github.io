---
title: 'Activate security auditing to log unsuccessful logon attempts'
date: '2001-01-09T23:00:15+01:00'
status: publish
permalink: /article/winnt-security-audit.html
author: Snakefoot
excerpt: 'Audit policies can be created to record unsuccessful logon attempts in the event log.'
type: post
id: 437
category:
    - 'User Security'
tag:
    - event-log
    - user-account
post_format: []
tags:
    - 'user-account,event-log'
---
It is possible to log unsuccessful logins to your machine, to detect if someone is trying to access your machine.  
  
 To do this:

1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to "Local Policies" -&gt; "Audit Policy"
3. For minimum logging select to audit failure in "Account Logon Events", "Directory Service Access" and "Logon Events"
 
 Note audits can also be useful when trying to figure out what keeps an application from working when started with user-privileges. The audits can show the failures that occurs when the application tries to access the needed folders and registry-entries. One can then change the Access Control List (ACL) for these resources, so access is granted when having user-privileges.  
  
 More info [MS KB300549](http://support.microsoft.com/kb/300549 "How To Enable and Apply Security Auditing in Windows 2000 [Q300549]")  
 More info [MS KB310399](http://support.microsoft.com/kb/310399 "How To Audit User Access of Files, Folders, and Printers in Windows XP [Q310399]")  
 More info [MS KB315416](http://support.microsoft.com/kb/315416 "HOW TO: Use Group Policy to Audit Registry Keys in Windows 2000 [Q315416]")  
 More info [MS KB324739](http://support.microsoft.com/kb/324739 "HOW TO: Use Group Policy to Audit Registry Keys in Windows Server 2003 [Q324739]")  