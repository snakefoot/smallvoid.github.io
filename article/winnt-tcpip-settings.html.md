---
title: 'Configure TCPIP stack settings in Windows NT'
date: '2001-01-01T22:33:34+01:00'
status: publish
permalink: /article/winnt-tcpip-settings.html
author: Snakefoot
excerpt: 'Description of the registry keys used for configuring the TCP/IP stack in Windows NT.'
type: post
id: 416
category:
    - Network
    - Network
    - Network
    - Network
tag:
    - lan
    - max-transfer-unit
    - network-performance
    - rwin
    - tcpip
    - wan
post_format: []
tags:
    - 'rwin,max-transfer-unit,lan,wan,tcpip,network-performance'
---
To configure the TCPIP stack for [optimal performance](/article/windows-tcpip-settings.html), then it is recommended to use utilities like [DrTCP or TCPIP Optimizer](/article/windows-tcpip-settings.html) especially if not feeling comfortable with the registry editor.  
  
 To configure default Receive WINdow (RWIN) in bytes:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  TcpWindowSize = 17520 (Standard Range = 0-65535, Window Scaling Range 0-1GByte, Default - calculated)  
>   
>  More Info [MS KB169789](http://support.microsoft.com/kb/169789 "High Rate of Collisions on 100-Megabit Networks [Q169789]")  
>  More Info [MS KB263088](http://support.microsoft.com/kb/263088 "Windows 2000 Does Not Use Configured TCPWindowSize Registry Parameter When Accepting a Connection [Q263088]")  
>  More Info [MS KB315237](http://support.microsoft.com/kb/315237 "High rate of collisions on 100-megabit networks [Q315237]")  
>  More Info [MS KB891371](http://support.microsoft.com/kb/891371 "The FTP connection does not use all available bandwidth to download a file in Windows Server 2003 [Q891371]")  
>   
>  Related : [Using PING to find the best TCP/IP RWIN](/article/tcpip-rwin-size.html)  
>  Related : [AFD will adjust the default TCPIP Receive Window](/article/winnt-winsock-buffer.html)

 To configure default receive window for a single adapter/interface in bytes (Win2k+ only):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{Adapter-id/GUID}\]  
>  TCPWindowSize = 17520  
>   
>  More Info [MS KB263088](http://support.microsoft.com/kb/263088 "Windows 2000 Does Not Use Configured TCPWindowSize Registry Parameter When Accepting a Connection [Q263088]")  
>  More Info [MS KB810382](http://support.microsoft.com/kb/810382 "Default TCP Window Size Is Still Used After You Specify a Different TCPWindowSize Value [Q810382]")

 To configure maximum receive window size for all interfaces in bytes. To ensure that Window Scaling doesn't create receive windows that takes too much memory (Win2k+ Only):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  GlobalMaxTcpWindowSize = 17520 (Standard Range = 0-65535, Window Scaling Range 0-1GByte, Default not set)

 To configure Time To Live (TTL):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  DefaultTTL = 64 (Range = 0-255, Default = 128)

 To configure Path MTU Black Hole Detection:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnablePMTUBHDetect = 0 (Enabled = 1, Disabled = 0, Default = 0)  
>   
>  Note Windows 2003 SP2, Windows XP SP3 and Windows Vista enables black hole detection by default, and changes the PMTU to 536 bytes if retransmissions occurs (If the following retransmission also fails then the PMTU is returned to its original size). More Info [MS KB925280](http://support.microsoft.com/kb/925280 "Changes in PMTU black hole router detection in Windows Server 2003 and in Windows Vista [Q925280]")  
>   
>  More Info [MS KB136970](http://support.microsoft.com/kb/136970 "PMTU Black Hole Detection Algorithm Change for Windows NT 3.51 [Q136970]")  
>  More Info [MS KB159211](http://support.microsoft.com/kb/159211 "Diagnoses and treatment of black hole routers [Q159211]")  
>  More Info [MS KB314825](http://support.microsoft.com/kb/314825 "How to Troubleshoot Black Hole Router Issues [Q314825]")

 To configure Path MTU Discovery:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnablePMTUDiscovery= 1 (Enabled = 1, Disabled = 0, Default = 1)

 To configure Selective Acknowledgments (ACK's) (Win2k+ Only):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  SackOpts = 1 (Enabled = 1, Disabled = 0, Default = 1)

 To configure Receive Window Scaling and Time Stamping (Win2k+ Only):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  Tcp1323Opts = 3 (Both Disabled = 0, Window Scaling Only = 1, Timestamp Only = 2, Both Enabled = 3, Default = No value; only initiate the options if requested.)  
>   
>  More Info [MS KB199947](http://support.microsoft.com/kb/199947 "TCP/IP: Windows NT 4.0 Does Not Support TCP Scale Option [Q199947]")

 To configure Max number of Duplicate Acknowledgments (ACK's) (WinNT4 Requires SP2):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  TcpMaxDupAcks = 2 (Range 1-3, Default = 2)  
>   
>  More Info [MS KB162179](http://support.microsoft.com/kb/162179 "TCP Fast Retransmit and Recovery Added in Windows NT 4.0 Service Pack 2 [Q162179]")

 Note none of these registry entries can be found in the registry after a clean install, so to return to the default values just delete the registry entries.  
  
 Related [Delayed TCPIP ACK can cause slow network throughput](/article/winnt-nagle-algorithm.html)  
 Related [Configure the max limit for concurrent TCP connections](/article/winnt-tcpip-max-limit.html)  
  
 More articles about the settings available for configuring the tcpip stack: - [MS KB140552](http://support.microsoft.com/kb/140552 "How to Optimize Windows NT to Run Over Slow WAN Links w/TCP/IP [Q140552]") - Minimize traffic over WAN.
- [MS KB819108](http://support.microsoft.com/kb/819108 "Settings for minimizing periodic WAN traffic [Q819108]") - Minimize traffic over WAN.
- [MS KB900926](http://support.microsoft.com/kb/900926 "Recommended TCP/IP settings for WAN links with a MTU size of less than 576 [Q900926]") - Using WAN with MTU less than 576
- [MS KB120642](http://support.microsoft.com/kb/120642 "TCP/IP and NetBT configuration parameters for Windows 2000 or Windows NT [Q120642]") - TCP/IP &amp; NBT Configuration Parameters for Windows NT and Windows 2000
- [MS KB224829](http://support.microsoft.com/kb/224829 "Description of Windows 2000 and Windows Server 2003 TCP Features [Q224829]") - Description of Windows 2000 and Windows Server 2003 TCP Features
- [MS KB314053](http://support.microsoft.com/kb/314053 "TCP/IP and NBT Configuration Parameters for Windows XP [Q314053]") - TCP/IP and NBT Configuration Parameters for Windows XP
- [MS KB142641](http://support.microsoft.com/kb/142641 "Internet server unavailable because of malicious SYN attacks [Q142641]") - Internet Server Unavailable Because of Malicious SYN Attacks
- [MS KB315669](http://support.microsoft.com/kb/315669 "How to harden the TCP/IP stack against denial of service attacks in Windows 2000 [Q315669]") - HOW TO: Harden the TCP/IP Stack Against Denial of Service Attacks in Windows 2000
- [MS KB324270](http://support.microsoft.com/kb/324270 "How to harden the TCP/IP stack against denial of service attacks in Windows Server 2003 [Q324270]") - HOW TO: Harden the TCP/IP Stack Against Denial of Service Attacks in Windows Server 2003
- [MS Technet](http://www.microsoft.com/technet/itsolutions/network/deploy/depovg/tcpip2k.mspx) - Microsoft Windows 2000 TCP/IP Implementation Details [Word Document](http://www.microsoft.com/windows2000/techinfo/howitworks/communications/networkbasics/tcpip_implement.asp)
- [MS Technet](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/networking/tcpip03.mspx) - Microsoft Windows Server 2003 TCP/IP Implementation Details
- [MS Technet](http://www.microsoft.com/technet/archive/security/prodtech/windows/iis/dosrv.mspx) - Security Considerations for Network Attacks
- [MS Technet](https://www.microsoft.com/technet/interopmigration/unix/sfu/perfnfs.mspx) - Performance Tuning Guidelines for Microsoft Services for Network File System
- [TCPIMP2.EXE &amp; TCPIPIMP.EXE](ftp://ftp.microsoft.com/bussys/winnt/winnt-docs/papers/) - WinNT TCPIP Whitepapers [Mirror](http://www.microsoft.com/ntserver/docs/TCPIP.DOC)
 
 Credits [regedit.com](http://registry.winguides.com/display.php/645/)  