---
title: 'UpTime utility for displaying the time since the last reboot'
date: '2001-01-01T16:48:38+01:00'
status: publish
permalink: /article/winnt-uptime.html
author: Snakefoot
excerpt: 'Uptime is a command line utility by Microsoft for displaying the time since the last reboot.'
type: post
id: 506
category:
    - Utilities
    - Utilities
tag:
    - uptime
post_format: []
tags:
    - uptime
---
[UpTime](http://www.microsoft.com/ntserver/nts/downloads/management/uptime/default.asp) is a command line tool that will show how long your Windows installation has been running without reboot.  
  
 One can also press CTRL+ALT+DEL and then see when the user was logged on.  
 If logging off several times a day a more correct way is to run this command, which shows when the [server service](/article/winnt-services-lanmanserver.html) was started:
 > net statistics server | more

 If using Windows Vista then this command will display the System Uptime (Or just open the Task Manager and see the Performance-tab):
 > cmd /k systeminfo | find "System Boot Time"