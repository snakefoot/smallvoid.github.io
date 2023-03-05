---
title: 'Configure SMB use of Netbios'
date: '2003-05-25T16:19:32+02:00'
status: publish
permalink: /article/winnt-smb-netbios.html
author: Snakefoot
excerpt: 'How to configure which port number to use for Netbios communcations.'
type: post
id: 148
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - dns
    - microsoft-network
    - netbios
post_format: []
tags:
    - 'netbios,microsoft-network,dns'
---
With Windows 2000 the first move away from Netbios was made. Instead DNS should be used for name resolution and SMB Direct Hosting at TCPIP port 445 for requests instead of port 139.  
  
 By standard both port 139 and 445 is open to get the highest degree of compatibility. A client will try to request on both ports and continue the communication on the port which responds first.  
  
 To disable SMB use of Netbios port 139 (Forces use of port 445):

1. On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**
2. Right-click **Internet facing connection**, and then click **Properties**.
3. Select **Internet Protocol TCP/IP** and select **Properties**
4. Click **Advanced** and select the **WINS** tab
5. Tick **Disable NetBIOS over TCP/IP** and click **Ok**
 
 To disable SMB use of port 445 with this DWORD (Forces use of port 139):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\NetBT \\Parameters\]  
>  SMBDeviceEnabled = 0  
>   
>  More Info [MS KB940684](http://support.microsoft.com/kb/940684 "No network provider accepted the given network path")

 To disable SMB use of port 139 and 445 (Disables nbt.sys driver):
1. Right-click **My Computer** on the desktop, and then click **Manage**.
2. Expand **System Tools**, and then select **Device Manager**.
3. Right-click **Device Manager**, point to **View**, and then click **Show hidden devices**.
4. Expand **Non-Plug and Play Drivers**.
5. Right-click **NetBios over Tcpip**, and then click **Disable**.
 
 To disable SMB completely:
1. On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**
2. Right-click **Internet facing connection**, and then click **Properties**.
3. Select **Client for Microsoft Networks**, and then click **Uninstall**.
4. Follow the uninstall steps.
5. Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.
6. Follow the uninstall steps.
 
 Related [Configure SMB signing in WinNT+](/article/winnt-smb-signing.html)  
  
 More Info [MS KB204279](http://support.microsoft.com/kb/204279 "Direct Hosting of SMB Over TCP/IP [Q204279]")  
 More Info [MS KB253959](http://support.microsoft.com/kb/253959 "Client for Microsoft Networks Functions When Unbound from Network Adapter [Q253959]")  
  
 Credits [ntsecurity.nu](http://ntsecurity.nu/papers/port445/)