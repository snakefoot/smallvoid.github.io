---
title: 'Reset WinSock/TCPIP or manage several network configs'
date: '2000-01-01T23:51:11+01:00'
permalink: /article/winnt-netsh.html
author: Snakefoot
excerpt: 'How to use the utility Netsh to reset or change the network configuration.'
type: post
id: 425
categories:
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - hardware-profile
    - netsh
    - tcpip
    - winsock
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
>  More info <a href="https://www.bing.com/search?q=KB+299357+Q299357" rel="nofollow" title="How to reset TCP/IP by using the NetShell utility [Q299357]">MS KB299357</a>

 Repair/re-init the Winsock interface if it has gone bad (Available in WinXP SP2 and Win2k3 SP1):
> netsh winsock reset  
>   
>  More info <a href="https://www.bing.com/search?q=KB+811259+Q811259" title="How to determine and recover from Winsock2 corruption [Q811259]" rel="nofollow">Repair Winsock and TCP/IP in WinXP/Win2k3 (MS KB811259)</a>  
>  More info <a href="https://www.bing.com/search?q=KB+837333+Q837333" title="How to repair network or modem connectivity issues in Windows 2000 [Q837333]" rel="nofollow">Repair Winsock and TCP/IP in Win2k (MS KB837333)</a>  
>  More info <a href="https://www.bing.com/search?q=KB+299451+Q299451" title="HOW TO: Remove and Reinstall TCP/IP on a Windows 2000 Domain Controllerr" rel="nofollow">Repair network for a Win2k Domain Controller (MS KB299451)</a>  
>  More info <a href="https://www.bing.com/search?q=KB+325356+Q325356" title="How to remove and reinstall TCP/IP on a Windows Server 2003 domain controller [Q325356]" rel="nofollow">Repair network for a Win2k3 Domain Controller (MS KB325356)</a>

 Note WinXP includes an option called **Alternative Configuration**, which is used when in a network without an available DHCP server, without needing to fiddle with netsh.
- On the **Start**-menu, click **Control Panel**.
- Click **Network and Internet Connections** and click **Network Connections**.
- Right-click the wanted connection and select **Properties**.
- Select **Internet Protocol (TCP/IP)** and press **Properties**.
- If the normal configuration is DHCP, then the **Alternate Configuration**-tab should be available. More info <a href="https://www.bing.com/search?q=KB+283676+Q283676" rel="nofollow" title="How to use the Alternate Configuration feature for multiple network connectivity in Windows XP [Q283676]">MS KB283676</a>
 
 More info <a href="https://www.bing.com/search?q=KB+242468+Q242468" rel="nofollow">How to Use the Netsh.exe Tool and Command-Line Switches (MS KB242468)</a>  
 More info <a href="https://www.bing.com/search?q=KB+257748+Q257748" rel="nofollow">Using NETSH to Change from Static IP to DHCP in Windows 2000 - (MS KB257748)</a>  
 More info <a href="https://www.bing.com/search?q=KB+254249+Q254249" rel="nofollow">NetSh Dump Does Not Completely Configure and Enable the RRAS (MS KB254249)</a>  
 More info <a href="https://www.bing.com/search?q=KB+281626+Q281626" rel="nofollow">How to Use the Netsh Utility to Export and Import DHCP Scopes (MS KB281626)</a>  
  
 Credits [is-it-true.org](http://www.is-it-true.org/)