---
title: 'Enable dumpster in Outlook to recover deleted messages'
date: '2004-11-26T18:58:36+01:00'
status: publish
permalink: /article/outlook-dumpster.html
author: Snakefoot
excerpt: 'When deleting a mail in Outlook, then it can still be restored through the Exchange server.'
type: post
id: 338
category:
    - Outlook
tag:
    - dumpster
    - email
post_format: []
tags:
    - 'dumpster,email'
---
When using Outlook and you have deleted a message, then the Exchange-server will by default retain deleted items, so they are recoverable 7 days. To recover a mail select the "Deleted Items"-folder go to Tools, Recover Deleted Items.  
  
 If doing a hard delete by holding down Shift+Delete to delete a message, then it is not moved to "Deleted Items"-folder. Making it impossible to recover such a deleted message the standard way. Instead one can apply the following registry key to enable recovery of messages from any folder:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Exchange \\Client \\Options\]  
>  DumpsterAlwaysOn = 1

 More info [MS KB178630](http://support.microsoft.com/kb/178630 "XADM: How to Recover Items That Are Not First Transferred to the Deleted Items Folder [Q178630]")  
 More info [MS KB246153](http://support.microsoft.com/kb/246153 "XCLN: How to Recover Items That Have Been Hard Deleted [Q246153]")  
  
 Credits [winnetmag.com](http://winnetmag.com/)