---
title: 'Activate security auditing to log unsuccessful logon attempts'
date: '2001-01-09T23:00:15+01:00'
permalink: /article/winnt-security-audit.html
author: Snakefoot
excerpt: 'Audit policies can be created to record unsuccessful logon attempts in the event log.'
type: post
id: 437
categories:
    - windows-2000_user-security
tags:
    - event-log
    - user-account
---
It is possible to log unsuccessful logins to your machine, to detect if someone is trying to access your machine.  
  
 To do this:

1. Start the [Local Security Policies](/article/winnt-group-policy-registry.html) snapin
2. In the tree-view go to "Local Policies" -&gt; "Audit Policy"
3. For minimum logging select to audit failure in "Account Logon Events", "Directory Service Access" and "Logon Events"
 
 Note audits can also be useful when trying to figure out what keeps an application from working when started with user-privileges. The audits can show the failures that occurs when the application tries to access the needed folders and registry-entries. One can then change the Access Control List (ACL) for these resources, so access is granted when having user-privileges.  
  
 More info <a href="https://www.bing.com/search?q=KB+300549+Q300549" rel="nofollow" title="How To Enable and Apply Security Auditing in Windows 2000 [Q300549]">MS KB300549</a>  
 More info <a href="https://www.bing.com/search?q=KB+310399+Q310399" rel="nofollow" title="How To Audit User Access of Files, Folders, and Printers in Windows XP [Q310399]">MS KB310399</a>  
 More info <a href="https://www.bing.com/search?q=KB+315416+Q315416" rel="nofollow" title="HOW TO: Use Group Policy to Audit Registry Keys in Windows 2000 [Q315416]">MS KB315416</a>  
 More info <a href="https://www.bing.com/search?q=KB+324739+Q324739" rel="nofollow" title="HOW TO: Use Group Policy to Audit Registry Keys in Windows Server 2003 [Q324739]">MS KB324739</a>  