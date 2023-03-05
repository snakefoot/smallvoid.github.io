---
title: 'Link Layer Topology Discovery (LLTD) Responder'
date: '2007-07-02T07:45:20+02:00'
status: publish
permalink: /article/winxp-lltd-responder.html
author: Snakefoot
excerpt: 'The LLTD protocol makes it easier to get an overview of the available network devices and their configuration.'
type: post
id: 651
category:
    - Network
tag:
    - link-layer-topology-discovery
    - lltd
    - network-topology
post_format: []
tags:
    - 'network-topology,link-layer-topology-discovery,lltd'
---
[Link Layer Topology Discovery (LLTD) Responder](http://go.microsoft.com/fwlink/?LinkId=70582) is a network protocol extension for Windows XP. Windows Vista has the ability to create a map of the entire computer network by using the LLTD protocol, but it will fail with devices that doesn't support this protocol. Windows XP will by default not appear on the network map, but if applying this update then it will.  
  
 More Info [Wiki: Link Layer Topology Discovery](http://en.wikipedia.org/wiki/Link_Layer_Topology_Discovery)  
 More Info [MS Technet](http://technet2.microsoft.com/WindowsVista/en/library/409fb2fa-8eb8-45af-b063-4f50f5a77b291033.mspx)  
  
 Note the LLTD installer will fail if trying to install on Windows 2003 (Locked to WinXP), but if changing the Compatibility mode of the installer to run as "Windows XP", then the LLTD installer will work on Win2k3. After the install then one has to [extract the files from the MSI package](/article/windows-extract-msi.html), and then manually install the new Network Protocol by selcecting that you Have disk and point it to rspndr.inf.