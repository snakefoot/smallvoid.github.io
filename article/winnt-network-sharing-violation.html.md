---
title: 'Configure automatic handling of network file sharing violations'
date: '2005-06-23T22:19:36+02:00'
status: publish
permalink: /article/winnt-network-sharing-violation.html
author: Snakefoot
excerpt: 'Sharing violations on files placed on network shares are retried while they block immediately with local files.'
type: post
id: 445
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - network-share
    - sharing-violation
post_format: []
tags:
    - 'network-share,sharing-violation'
---
A sharing violation happens when one program requests exclusive access to a file (ex. to write to the file), while another program is already having the file open (ex. to read the file). When a sharing violation happens on a local file, then the request for write-access will fail at once.  
 When a sharing violation happens on a network file, then the [Server service](/article/winnt-services-lanmanserver.html) on the remote machine will detect the sharing violation, but instead of failing right away, then it retries to open the file with certain intervals.  
  
 This retry mechanism is quite nice when using programs in a network environment, which haven't been made to handle sharing violation, as it will lower the "visible" sharing violations. If the programs trying to access the same file is already capable of handling the sharing violation, with their own retry mechanism, then this change in behavior with network files might interfere, and lower performance.

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\LanmanServer \\Parameters\]  
>  SharingViolationDelay = 200 (Default = 200 ms)  
>  SharingViolationRetries = 5 (Default = 5)  
>   
>  More Info [MS KB150384](http://support.microsoft.com/kb/150384 "Shared file access is delayed if the file is open on another computer [Q150384]")  
>  More Info [MS KB889588](http://support.microsoft.com/kb/889588 "How to optimize Office Access and Jet database engine network performance with Windows 2000-based and Windows XP-based clients [Q889588]")

 Note it is strange that Microsoft have implemented this polling strategy, incase several programs are trying to request the same file, then one or more programs might experience that they never gets access because between each delay another program "steals" the access.  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)