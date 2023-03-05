---
title: 'Configure several IP Addresses for a single network adapter'
date: '2002-10-13T22:05:35+02:00'
status: publish
permalink: /article/win9x-multiple-subnets.html
author: Snakefoot
excerpt: 'How to configure a network adapter to be part of multiple subnets.'
type: post
id: 202
category:
    - Network
    - Network
    - Network
tag:
    - subnet
    - tcpip
post_format: []
tags:
    - 'tcpip,subnet'
---
If wanting to part of several subnets using only one network adapter, then one is not able to do it through the GUI.  
  
 But it can be done through the registry by updating these STRING values (Separating the IP-Addresses with a comma ","):

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Class \\NetTrans \\{Adapter-Id}\]  
>  IPAddress = "192.168.1.3,10.0.0.1"  
>  IPMask = "255.255.255.0,255.0.0.0"

 The {Adapter-Id} can have the value 0000, 0001, 000n. If several {Adapter-Id}, then find the correct one using the following ways:
- Looking at the value "DriverDesc" for each {Adapter-Id}, and see if it matches the wanted device (Ex. if modem then "Dialup Adapter")
- Change the TCP/IP setting for the adapter in network properties, example the DNS address. Then find the {Adapter-Id} which has that certain DNS-address
 
 Note if one of the subnets should be configured by the local DHCP server, then add an entry with "0.0.0.0" as IP- and subnet-address.  
  
 More info [MS KB156772](http://support.microsoft.com/kb/156772 "Adding Additional IP Addresses to a Single Network Adapter [Q156772]")  
  
 Credits [mydesktophelp.com](http://mydesktophelp.com/)