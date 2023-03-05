---
title: 'Fix the automatic email notification in Outlook'
date: '2006-03-11T19:02:42+01:00'
status: publish
permalink: /article/outlook-email-notification.html
author: Snakefoot
excerpt: 'Possible solutions when Outlook doesn''t recieve instant email notifications from the Exchange server.'
type: post
id: 339
category:
    - Outlook
tag:
    - email-notification
post_format: []
tags:
    - email-notification
---
Microsoft Exchange Server uses UDP to broadcast notifications about the arrival of new mails. If a firewall/router is blocking for UDP traffic, then the automatic notification of new emails will fail. Instead one have to press Send/Receive, or change to another Outlook folder and then change back to the Inbox to receive new emails.  
  
 To fix the automatic email notification use one of the following methods:

- Configure the NAT to allow UDP traffic, and configure the firewall to make an exception for Outlook.exe, and configure the ForcePolling setting to 0 (Instead of 1 as shown in the bullet below) so Outlook will listen for UDP messages.  
    
   By default Outlook opens a dynamic UDP port (1024 - 65535) so one should create a firewall rule at application level. Outlook 2003/2007 makes it possible to specify a fixed UDP port using this DWORD registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Office \\12w.0 \\Outlook \\RPC\]  
  >  FixedUDPPort = ? (Outlook 2007)  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Office \\11.0 \\Outlook \\RPC\]  
  >  FixedUDPPort = ? (Outlook 2003)
  
   More Info [MS KB839226](http://support.microsoft.com/kb/839226 "The Outlook Find feature and the new mail notifications do not work after you apply Windows XP Service Pack 2")
- Configure Outlook to poll the exchange server instead of using UDP, by creating the following registry keys:
  > \[HKEY\_CURRENT\_USER \\Software \\Policies \\Microsoft \\Office \\&lt;ver&gt; \\Outlook \\RPC\]  
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Office \\&lt;ver&gt; \\Outlook \\RPC\]  
  >  ForcePolling = 1 (1 = Use RPC by default, 0 = Only use RPC if UDP fails)  
  >   
  >  Outlook 2000 (&lt;ver&gt; = 9.0), requires Microsoft Office 2000 Service Pack 3  
  >  Outlook 2002 (&lt;ver&gt; = 10.0), requires Microsoft Office XP Service Pack 1  
  >  Outlook 2003 (&lt;ver&gt; = 11.0)  
  >   
  >  More info [MS KB304849](http://support.microsoft.com/kb/304849 "You cannot receive a new e-mail notifications in Outlook 2000 when you use the Network Address Translation [Q304849]")  
  >  More info [MS KB305572](http://support.microsoft.com/kb/305572 "You cannot receive new e-mail notifications in environments that use the Network Address Translation in Outlook 2002 [Q305572]")  
  >  More info [MS KB311506](http://support.microsoft.com/kb/311506 "OL2000: You Cannot Receive New E-mail Notifications [Q311506]")
  
   Note the default interval between each RPC poll is 60 seconds, and is controlled by the Exchange Server. Therefore users who are using polling will not experience instant delivery, even when sending messages within the organisation.