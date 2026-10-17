---
title: 'Configure the priority of protocols bound to the network'
date: '2003-12-30T23:11:30+01:00'
permalink: /article/winnt-protocol-priority.html
author: Snakefoot
excerpt: 'Change which network protocol to use first when looking for a resource on the network.'
type: post
id: 420
categories:
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - netbeui
    - network-protocol
    - network-redirector
    - tcpip
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
  - Vista will only display the Advanced menu-item when pressing the ALT-key. More Info <a href="https://www.bing.com/search?q=KB+935310+Q935310" rel="nofollow" title="You experience connectivity issues">MS KB935310</a>.
4. Select the **Adapter and Bindings** tab and in **Advanced Settings - Connections** select the network connection to configure bindings for.
5. In **Bindings for Local Area Connections:** set the order of protocols for each service for the selected connection.
 
 More Info <a href="https://www.bing.com/search?q=KB+266771+Q266771" rel="nofollow" title="HOW TO: Change the Binding Order in Windows 2000 [Q266771]">MS KB266771</a>  
  
 Related [Configure the priority of network adapters and gateways](/article/network-gateway-metric.html)  
 Related [Configure the priority of networks known by the MUP](/article/winnt-network-priority.html)  