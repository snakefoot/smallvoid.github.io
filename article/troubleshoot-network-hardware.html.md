---
title: 'Diagnose performance issues with network hardware'
date: '2003-09-24T20:21:15+02:00'
status: publish
permalink: /article/troubleshoot-network-hardware.html
author: Snakefoot
excerpt: 'Description of different causes and solutions to network problems.'
type: post
id: 197
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - dialup-modem
    - internet
    - lan
    - network-diagnostic
    - network-interface-card
    - network-performance
    - network-router
    - network-switch
    - tcpip
    - wan
post_format: []
tags:
    - 'lan,wan,internet,tcpip,network-switch,network-router,dialup-modem,network-performance,network-diagnostic,network-interface-card'
---
Several factors can affect the performance or the connectivity of a network:

- If using Ethernet and mixing Half-Duplex with Full-Duplex (Or using Automatic Detection / Autosense) 
  - If using a hub force all to use Half-Duplex
  - If using a switch force all to use Full-Duplex (If using a Switch with management software then remember to check that the ports are configured properly)
- If using Ethernet and connecting more than 8 people to a Hub, then collisions will come at higher load because the Hub broadcasts 
  - Use a Ethernet Switch instead, which doesn't broadcast, if needing a larger network
- If a single computer is experiencing connection dropouts or slow speed: 
  - Check the connection to the network. Try a different cable that have proven to work, Try a different port on the hub/switch that have proven to work, Try a different network adapter.
  - If the computer has an IDE hard disk installed, then [check that the IDE HDD is configured properly](/article/troubleshoot-hdd-dma.html).
  - If slow file copy performance then try other file transfer protocols like FTP, HTTP, Microsoft Network etc., as problem can be caused a misconfigured file sharing protocol.
  - Test the overall network performance using the very simple PING protocol, by launching multiple large packet PING commands against the machine to test its network bandwidth capabilities:
  > ping 10.0.0.5 -l 65500 -t
  - Check drivers and operating system by uninstalling the network adapter along with network protocols and reinstall it again (Maybe check for [ghost devices](/article/winnt-ghost-devices.html))
  - Check for [hardware/software conflicts](/article/repair-hardware-conflict.html). If an addon Network Adapter, then try to place it in a different PCI slot so it doesn't share IRQ. If onboard, then try to disable other unnecessary onboard devices and rearrange PCI addon cards.
 
 Several factors can affect the performance of the Internet connection:
  - The cable from your computer to the router/modem might be bended and disturb the signal 
  - Check whether messing with the cable improves things, or if possible change it with a new one
- The cable from your router/modem to the wall outlet might be bended and disturb the signal 
  - Check whether messing with the cable improves things, or if possible change it with a new one
- Other devices attached to the same wall outlet or placed nearby might disturb the signal (A phone can disturb a modem or DSL line) 
  - Unplug unneeded devices like speakers, phones, television to see if it is the case
- The cable from your wall outlet to the ISP Central might be of bad quality and lower the max bandwidth 
  - Usually on request the ISP can measure the quality of the connection quality of the line
- The ISP is having problems with its own servers or routers (Affecting a large group of customers) 
  - Check the ISP maintenance web-page, newsgroup or telephone to see if it is the case (Usually it is solved within an hour)
  - Test the connection to a public server (like Google or other local ISP) to see if there is a problem with a router (ping drops, slow ping times no connection beyond it) using a combined tracert and ping tool like [WinMTR](http://winmtr.sourceforge.net/)
- If using a DialUp-modem, then it might be configured to use options not supported by your ISP 
  - Contact your ISP support and ask them for how to configure your modem to match their configuration
 
 Related [Creating a Local Area Network (LAN)](/article/troubleshooting-network.html)