---
title: 'Description of Automatic TCP/IP Addressing'
date: '2005-11-26T03:32:18+01:00'
status: publish
permalink: /article/automatic-tcpip-addressing.html
author: Snakefoot
excerpt: 'Details of how the Automatic Private IP Addressing (APIPA) takes over if no DHCP server is found.'
type: post
id: 141
category:
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - APIPA
    - dhcp
    - tcpip
post_format: []
tags:
    - 'APIPA,dhcp,tcpip'
---
It can be a daunting task to [Setup a home network](/article/troubleshooting-network.html), because the default network configuration requires that a DCHP server is present on the network. Sometimes the ISP router/modem can act as DHCP server and provide the proper network configuration, but if this isn't the case then all computers end up with 0.0.0.0 / 0.0.0.0 as IP address and cannot connect to anything on the network.  
  
 This is where Automatic Private IP Addressing (APIPA) steps in and tries to save the day, it continues to chooses a random IP address within the range 169.254.x.x / 255.255.0.0 until it finds a unique IP that doesn't conflict with other computers IP. When a computer is configured with APIPA, then it can only connect to other computers that are also configured with APIPA.  
  
 Note a computer only attempts to use APIPA when configured to use a DHCP server and it doesn't respond (timeouts). When assigned an IP from APIPA, then the computer will continue to search for a DHCP server, by sending out a DHCP request every 5 minutes.  
  
 To configure the use of APIPA in Windows 98/Me:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\VxD \\DHCP\]  
>  IPAutoconfigurationEnabled = 1 (Default = 1)  
>   
>  Note to see if using APIPA then start WinIpCfg.exe and check that the IP address begins with 169.254.x.x

 To configure the use of APIPA in Windows 2000/XP:
 
 > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
 >  IPAutoconfigurationEnabled = 1 (Default = 1)  
   
 Note to see if using APIPA then start a command prompt (cmd) and run this command "ipconfig /all", and check that the IP address begins with 169.254.x.x

 Related [Faster boot times by using static IP instead of DHCP](/article/dhcp-static-ip.html)  
  
 More Info [MS KB188480](http://support.microsoft.com/kb/188480 "Windows 98 Mtsutil.txt File [Q188480]")  
 More Info [MS KB220874](http://support.microsoft.com/kb/220874 "How to Use Automatic TCP/IP Addressing Without a DHCP Server [Q220874]")  
 More Info [MS KB255836](http://support.microsoft.com/kb/255836 "Change in DHCP Client Behavior in Windows 2000 [Q255836]")  
 More Info [MS KB244268](http://support.microsoft.com/kb/244268 "Routing Does Not Work When Multiple Adapters Use Automatic Private IP Addressing Simultaneously [Q244268]")  