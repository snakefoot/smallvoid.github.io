---
title: 'Creating a Local Area Network (LAN)'
date: '2002-05-28T03:44:22+02:00'
status: publish
permalink: /article/troubleshooting-network.html
author: Snakefoot
excerpt: 'Setting up a computer network, and steps for troubleshooting errors in the computer network.'
type: post
id: 142
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - lan
    - microsoft-network
    - network-diagnostic
    - network-interface-card
post_format: []
tags:
    - 'lan,microsoft-network,network-diagnostic,network-interface-card'
---
The recipe is quite simple to create a home network to share files between computers:

1. Install network adapter in the computer and install the driver in Windows.
2. Configure the network adapter in Windows: 
  1. Install the protocol "Internet Protocol TCP/IP" and configure it to use [DHCP or static IP](/article/dhcp-static-ip.html) and enable "Netbios"
  2. Install the client "Client for Microsoft Networks"
  3. Install the service "Files and Printer Sharing for Microsoft Networks"
3. Create the file shares in Windows for the other computers to access.
4. Connect all computers in the work to the hub/switch using network cables (or use a cross over cable to connect directly to another computer).
 
 Now if the computer network is not working now, then it is time to start troubleshooting what is wrong. The two most important tools are both command line tools and should be used from a command prompt:
- **ping** - Can tell if another computer is connected with a certain IP address.
- **ipconfig** - Can tell the IP address assigned to the computer.
 
 Cannot ping local machine, check the following:
- Check that it is the correct IP Address (static 192.168.0.2 / 255.255.255.0)
- Check if a firewall is blocking, by disabling or reconfiguring it
- Reinstall the TCP/IP protocol
- Reinstall network adapter (Maybe try other drivers)
- Check if bad network adapter, by trying another adapter
 
 Cannot ping remote machine, check the following:
- Check that the remote machine is using the correct IP Address (static 192.168.0.3 / 255.255.255.0)
- Check that the remote machine can ping itself
- Check if a firewall is blocking, by disabling or reconfiguring it
- Check if it is a bad cable, by trying another cable
- Check if it is a bad HUB/Switch port, by trying another port
 
 Cannot access/see/browse the local machine/shares on the network, then check the following:
- Check that the local machine can be pinged
- Check that one can access the share directly \\\\LOCAL\_MACHINE, if success then the network just need to be given time. Or it can be a [hidden share](/article/hidden-file-shares.html) or [hidden machine](/article/winnt-hide-network.html)
- Check that File Sharing is installed and bound to the TCP/IP protocol
- Check that Netbios is installed for the TCP/IP protocol
- Check that firewall is not blocking, by disabling or reconfiguring it
 
 Cannot access/see/browse the remote machine/shares on the Network, then check the following:
- Check that the remote machine can be pinged
- Check that the remote machine can see its local shares
- Check that the remote machine is part of the same workgroup
- Check that one can access the share directly \\\\REMOTE\_MACHINE, if success then the network just need to be given time. Or it can be a [hidden share](/article/hidden-file-shares.html) or [hidden machine](/article/winnt-hide-network.html)
- If using WinNT+ then check that users and security has been setup properly: 
  - [How to enable Win9x filesharing in Windows 2000](/article/win2k-win9x-filesharing.html)
  - [How to enable Win9x filesharing in Windows XP](/article/winxp-win9x-filesharing.html)
- Check that a firewall on the remote machine is not blocking, by disabling or reconfiguring it
 
 Related [Check that network hardware is configured properly](/article/troubleshoot-network-hardware.html)  
 Related [Lock down the network connection](/article/windows-network-lockdown.html)  
  
 More Info [MS KB102908](http://support.microsoft.com/kb/102908 "How to Troubleshoot TCP/IP Connectivity with Windows 2000 or Windows NT [Q102908]")  
 More Info [MS KB169790](http://support.microsoft.com/kb/169790 "How to Troubleshoot Basic TCP/IP Problems [Q169790]")  
 More Info [MS KB289256](http://support.microsoft.com/kb/289256 "A Description of the Repair Option on a Local Area Network or High-Speed Internet Connection [Q289256]")  
 More Info [MS KB314067](http://support.microsoft.com/kb/314067 "How to Troubleshoot TCP/IP Connectivity with Windows XP [Q314067]")  
 More Info [MS KB323388](http://support.microsoft.com/kb/323388 "HOW TO: Diagnose and Test TCP/IP or NetBIOS Network Connections in Windows Server 2003 [Q323388]")  
 More Info [MS KB325487](http://support.microsoft.com/kb/325487 "How to Troubleshoot Network Connectivity Problems [Q325487]")  