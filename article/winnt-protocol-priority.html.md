---
title: 'Configure the priority of protocols bound to the network'
date: '2003-12-30T23:11:30+01:00'
status: publish
permalink: /article/winnt-protocol-priority.html
author: Snakefoot
excerpt: 'Change which network protocol to use first when looking for a resource on the network.'
type: post
id: 420
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - netbeui
    - network-protocol
    - network-redirector
    - tcpip
post_format: []
tags:
    - 'network-redirector,tcpip,netbeui,network-protocol'
---
When a network service/redirector (Like Microsoft Network or Novell Network) needs to make a network request it has to use a protocol. To get the fastest responses one should assign the highest priority to the protocol (Like "TCPIP" or "NetBEUI"), which gives access to the majority of the wanted network resources. Another way is to unbind/disable/uninstall protocols, which are not necessary for accessing resources on that network.  
  
 To configure the priority of protocols in WinNT4:

1. Open **Control Panel**
2. Double click **Network** applet
3. Select **Bindings** tab
4. Show bindings for **All Services** and change the order of protocols for each service
 
 To configure the priority of protocols in Win2k/XP:
1. Open **Control Panel**
2. Double click **Network and Dial-Up Connections**
3. In the menu select **Advanced** and select **Advanced Settings...**
  - Vista will only display the Advanced menu-item when pressing the ALT-key. More Info [MS KB935310](http://support.microsoft.com/kb/935310 "You experience connectivity issues").
4. Select the **Adapter and Bindings** tab and in **Advanced Settings - Connections** select the network connection to configure bindings for.
5. In **Bindings for Local Area Connections:** set the order of protocols for each service for the selected connection.
 
 More Info [MS KB266771](http://support.microsoft.com/kb/266771 "HOW TO: Change the Binding Order in Windows 2000 [Q266771]")  
  
 Related [Configure the priority of network adapters and gateways](/article/network-gateway-metric.html)  
 Related [Configure the priority of networks known by the MUP](/article/winnt-network-priority.html)  