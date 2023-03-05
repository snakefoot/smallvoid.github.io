---
title: 'Using NULL sessions to view shares and user accounts'
date: '2002-02-06T16:12:41+01:00'
status: publish
permalink: /article/winnt-null-session.html
author: Snakefoot
excerpt: 'Example of how to list shares and user accounts with anonymous access.'
type: post
id: 147
category:
    - 'User Security'
    - 'User Security'
    - 'User Security'
    - 'User Security'
tag:
    - anonymous-access
    - null-session
    - user-account
post_format: []
tags:
    - 'null-session,anonymous-access,user-account'
---
It is possible to access the [IPC$ share](/article/winnt-ipc-share.html) with a null session, after that one can access information about the machine configuration.  
  
 How to create a null session:

> net use \\\\IP\_ADDRESS\\ipc$ "" /user:""

 How to access shares after creation of null session:
 > net view \\\\IP\_ADDRESS

 How to list administrators after creation of null session:
 > local administrators \\\\IP\_ADDRESS

 How to list group members in "domain admins" after creation of null session:
 > global "domain admins" \\\\IP\_ADDRESS

 The utilities [local.exe](ftp://ftp.microsoft.com/bussys/winnt/winnt-public/reskit/nt40/i386/local.exe) and [global.exe](ftp://ftp.microsoft.com/bussys/winnt/winnt-public/reskit/nt40/i386/global.exe). They are part of the Windows NT Resource Kit. [WInfo](http://ntsecurity.nu/toolbox/winfo/) is a 3rd party utility that also can exploit null sessions.  
  
 Disabling Netbios or blocking the ports 137-139 doesn't close for Null-Sessions, unless one also closes the [SMB on port 445](/article/winnt-smb-netbios.html).  
  
 Related [Restrict access to NULL sessions](/article/winnt-restrict-anonymous.html)  
  
 More Info [MS KB132679](http://support.microsoft.com/kb/132679 "Local System Account and Null Sessions in Windows NT [Q132679]")  
 More Info [MS KB289655](http://support.microsoft.com/kb/289655 "HOW TO: Enable Null Session Shares on a Windows 2000-Based Computer [Q289655]")  
  
 Credits [The Hack FAQ](http://www.nmrc.org/pub/faq/hackfaq/)