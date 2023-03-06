---
title: 'Configure the file association for unknown file types'
date: '2004-11-19T21:19:35+01:00'
status: publish
permalink: /article/winnt-file-association.html
author: Snakefoot
excerpt: 'Change whether it should use the Internet to determine what application to use for opening a file of an unknown type.'
type: post
id: 411
category:
    - Desktop
    - Desktop
tag:
    - file-association
    - unknown-file
post_format: []
tags:
    - 'file-association,unknown-file'
---
Windows XP introduced a new features for configuring the file association for unknown file types. When trying to open a file which Windows doesn't recognize, then it will present you with two options:

- Use the Web service to find the appropriate program
- Select the program from a list
 
 The Web service redirects one to ex. <http://shell.windows.com/fileassoc/0409/xml/redir.asp?Ext=rar>, which presents different options for opening the file. One might get annoyed by this extra dialog, and it is possible to disable it.
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  InternetOpenWith = 0  
>   
>  \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\System\]  
>  NoInternetOpenWith = 1  
>   
>  More Info [MS Technet: File Association Web Service](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/xpmanaged/09_xpfil.mspx "Using Windows XP Professional with Service Pack 1 in a Managed Environment")

 Credits [windowsxp.mvps.org](http://windowsxp.mvps.org/)