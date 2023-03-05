---
title: 'Display detected network errors in connection status'
date: '2002-02-02T00:03:44+01:00'
status: publish
permalink: /article/winnt-detect-network-error.html
author: Snakefoot
excerpt: 'Network connection status can be extended to also show errors besides bytes/packets received and sent.'
type: post
id: 427
category:
    - Network
    - Network
    - Network
tag:
    - lan
    - retransmission
    - wan
post_format: []
tags:
    - 'retransmission,lan,wan'
---
In the Connection Status dialog box on the general tab it is possible to see how many errors (Retransmissions) it has detected. This can be useful if lacking proper network monitoring tools.  
  
 To enable this error counting one have to create this DWORD key in the registry :

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Network \\Connections \\StatMon\]  
>  ShowLanErrors=1 (Disabled = 0, Enabled = 1, Default = 0)

 Note due to a bug the display of errors is placed a little odd in the dialog box.  
  
 Note the Status dialog box also shows the amount of data received and sent, though sometimes it is shown in packets and other times it is shown in bytes. This behavior is caused by the drivers used for the network adapter or dialup-modem. If on a Ethernet LAN, then one have the possibility to see how much data(in bytes) that has been sent and received by opening a cmd-prompt and execute this command:
 > netstat -e

 Credits [Marshall University Win2k Project](http://www.marshall.edu/UCS/Windows/)