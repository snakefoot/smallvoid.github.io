---
title: 'Uninstall or reinstall NetMeeting in Windows NT'
date: '2004-05-02T01:05:14+02:00'
status: publish
permalink: /article/winnt-install-netmeeting.html
author: Snakefoot
excerpt: 'NetMeeting is an inter-message (IM) application by Microsoft which can create a virtual conference room for several users to chat and exchange documents.'
type: post
id: 468
category:
    - Troubleshoot
    - Troubleshoot
tag:
    - netmeeting
    - uninstall
post_format: []
tags:
    - 'netmeeting,uninstall'
---
NetMeeting is installed no matter if you want it or not. It is possible to uninstall it with this command:

> %SystemRoot%\\System32\\rundll32.exe setupapi,InstallHinfSection NetMtg.Remove 132 msnetmtg.inf  
>   
>  More Info [MS KB267958](http://support.microsoft.com/kb/267958 "HOW TO: Remove and then Reinstall NetMeeting [Q267958]")

 To reinstall NetMeeting again after uninstalling it:
1. Find the file C:\\Windows\\Inf\\**msnetmtg.inf**
2. Select and Right click the file and choose to **Install**
 
 Note if using WinXP and actually want to use NetMeeting, then one can add it to the Start-menu by executing this command:
> conf  
>   
>  More Info [MS KB298327](http://support.microsoft.com/kb/298327 "NetMeeting Is Not Available on the Windows XP "Communications" Menu [Q298327]")

 More Info [Microsoft NetMeeting "How-To" Guide](http://support.microsoft.com/support/netmeeting/howto/default.asp)  