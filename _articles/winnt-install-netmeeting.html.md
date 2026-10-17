---
title: 'Uninstall or reinstall NetMeeting in Windows NT'
date: '2004-05-02T01:05:14+02:00'
permalink: /article/winnt-install-netmeeting.html
author: Snakefoot
excerpt: 'NetMeeting is an inter-message (IM) application by Microsoft which can create a virtual conference room for several users to chat and exchange documents.'
type: post
id: 468
categories:
    - windows-2000_troubleshoot
    - windows-xp_troubleshoot
tags:
    - netmeeting
    - uninstall
---
NetMeeting is installed no matter if you want it or not. It is possible to uninstall it with this command:

> %SystemRoot%\\System32\\rundll32.exe setupapi,InstallHinfSection NetMtg.Remove 132 msnetmtg.inf  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20267958%20Q267958" rel="nofollow" title="HOW TO: Remove and then Reinstall NetMeeting [Q267958]">MS KB267958</a>

 To reinstall NetMeeting again after uninstalling it:
1. Find the file C:\\Windows\\Inf\\**msnetmtg.inf**
2. Select and Right click the file and choose to **Install**
 
 Note if using WinXP and actually want to use NetMeeting, then one can add it to the Start-menu by executing this command:
> conf  
>   
>  More Info <a href="https://www.bing.com/search?q=KB%20298327%20Q298327" rel="nofollow" title="NetMeeting Is Not Available on the Windows XP 'Communications' Menu [Q298327]">MS KB298327</a>

 More Info [Microsoft NetMeeting "How-To" Guide](http://support.microsoft.com/support/netmeeting/howto/default.asp)  