---
title: 'Reset WinSock/TCPIP or manage several network configs'
date: '2000-01-01T23:51:11+01:00'
status: publish
permalink: /article/winnt-netsh.html
author: Snakefoot
excerpt: 'How to use the utility Netsh to reset or change the network configuration.'
type: post
id: 425
category:
    - Network
    - Network
    - Network
tag:
    - hardware-profile
    - netsh
    - tcpip
    - winsock
post_format: []
tags:
    - 'netsh,hardware-profile,tcpip,winsock'
---
If having a laptop which you use in different networks (Home, Work, Customer, etc.), then one can use NetShell to backup each network configuration and restore them again at will. NetShell replaces Routemon from WinNT4.  
  
 To backup a configuration :

> netsh -c interface dump &gt; c:\\configs\\officeinterface.txt

 To restore a configuration :  
> netsh -f c:\\configs\\officeinterface.txt

 When using NetShell to change network settings it doesn't require a reboot. One can also use hardware profiles to save the network configuration, but it will require a reboot to change from one hardware profile to another.  
  
 Repair/reinit the TCP/IP protocol if it has gone bad (Useful as WinXP cannot uninstall the TCPIP stack):
> netsh int ip reset  
>   
>  More info [MS KB299357](http://support.microsoft.com/kb/299357 "How to reset TCP/IP by using the NetShell utility [Q299357]")

 Repair/re-init the Winsock interface if it has gone bad (Available in WinXP SP2 and Win2k3 SP1):
> netsh winsock reset  
>   
>  More info [Repair Winsock and TCP/IP in WinXP/Win2k3 (MS KB811259)](http://support.microsoft.com/kb/811259 "How to determine and recover from Winsock2 corruption [Q811259]")  
>  More info [Repair Winsock and TCP/IP in Win2k (MS KB837333)](http://support.microsoft.com/kb/837333 "How to repair network or modem connectivity issues in Windows 2000 [Q837333]")  
>  More info [Repair network for a Win2k Domain Controller (MS KB299451)](http://support.microsoft.com/kb/299451 "HOW TO: Remove and Reinstall TCP/IP on a Windows 2000 Domain Controllerr")  
>  More info [Repair network for a Win2k3 Domain Controller (MS KB325356)](http://support.microsoft.com/kb/325356 "How to remove and reinstall TCP/IP on a Windows Server 2003 domain controller [Q325356]")

 Note WinXP includes an option called **Alternative Configuration**, which is used when in a network without an available DHCP server, without needing to fiddle with netsh.
- On the **Start**-menu, click **Control Panel**.
- Click **Network and Internet Connections** and click **Network Connections**.
- Right-click the wanted connection and select **Properties**.
- Select **Internet Protocol (TCP/IP)** and press **Properties**.
- If the normal configuration is DHCP, then the **Alternate Configuration**-tab should be available. More info [MS KB283676](http://support.microsoft.com/kb/283676 "How to use the Alternate Configuration feature for multiple network connectivity in Windows XP [Q283676]")
 
 More info [How to Use the Netsh.exe Tool and Command-Line Switches (MS KB242468)](http://support.microsoft.com/kb/242468)  
 More info [Using NETSH to Change from Static IP to DHCP in Windows 2000 - (MS KB257748)](http://support.microsoft.com/kb/257748)  
 More info [NetSh Dump Does Not Completely Configure and Enable the RRAS (MS KB254249)](http://support.microsoft.com/kb/254249)  
 More info [How to Use the Netsh Utility to Export and Import DHCP Scopes (MS KB281626)](http://support.microsoft.com/kb/281626)  
  
 Credits [is-it-true.org](http://www.is-it-true.org/)