---
title: 'Configure TCPIP stack settings in Windows NT'
date: '2001-01-01T22:33:34+01:00'
permalink: /article/winnt-tcpip-settings.html
author: Snakefoot
excerpt: 'Description of the registry keys used for configuring the TCP/IP stack in Windows NT.'
type: post
id: 416
categories:
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - lan
    - max-transfer-unit
    - network-performance
    - rwin
    - tcpip
    - wan
---
To configure the TCPIP stack for [optimal performance](/article/windows-tcpip-settings.html), then it is recommended to use utilities like [DrTCP or TCPIP Optimizer](/article/windows-tcpip-settings.html) especially if not feeling comfortable with the registry editor.  
  
 To configure default Receive WINdow (RWIN) in bytes:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  TcpWindowSize = 17520 (Standard Range = 0-65535, Window Scaling Range 0-1GByte, Default - calculated)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+169789+Q169789" rel="nofollow" title="High Rate of Collisions on 100-Megabit Networks [Q169789]">MS KB169789</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+263088+Q263088" rel="nofollow" title="Windows 2000 Does Not Use Configured TCPWindowSize Registry Parameter When Accepting a Connection [Q263088]">MS KB263088</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+315237+Q315237" rel="nofollow" title="High rate of collisions on 100-megabit networks [Q315237]">MS KB315237</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+891371+Q891371" rel="nofollow" title="The FTP connection does not use all available bandwidth to download a file in Windows Server 2003 [Q891371]">MS KB891371</a>  
>   
>  Related : [Using PING to find the best TCP/IP RWIN](/article/tcpip-rwin-size.html)  
>  Related : [AFD will adjust the default TCPIP Receive Window](/article/winnt-winsock-buffer.html)

 To configure default receive window for a single adapter/interface in bytes (Win2k+ only):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters \\Interfaces \\{Adapter-id/GUID}\]  
>  TCPWindowSize = 17520  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+263088+Q263088" rel="nofollow" title="Windows 2000 Does Not Use Configured TCPWindowSize Registry Parameter When Accepting a Connection [Q263088]">MS KB263088</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+810382+Q810382" rel="nofollow" title="Default TCP Window Size Is Still Used After You Specify a Different TCPWindowSize Value [Q810382]">MS KB810382</a>

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
>  Note Windows 2003 SP2, Windows XP SP3 and Windows Vista enables black hole detection by default, and changes the PMTU to 536 bytes if retransmissions occurs (If the following retransmission also fails then the PMTU is returned to its original size). More Info <a href="https://www.bing.com/search?q=KB+925280+Q925280" rel="nofollow" title="Changes in PMTU black hole router detection in Windows Server 2003 and in Windows Vista [Q925280]">MS KB925280</a>  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+136970+Q136970" rel="nofollow" title="PMTU Black Hole Detection Algorithm Change for Windows NT 3.51 [Q136970]">MS KB136970</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+159211+Q159211" rel="nofollow" title="Diagnoses and treatment of black hole routers [Q159211]">MS KB159211</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+314825+Q314825" rel="nofollow" title="How to Troubleshoot Black Hole Router Issues [Q314825]">MS KB314825</a>

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
>  More Info <a href="https://www.bing.com/search?q=KB+199947+Q199947" rel="nofollow" title="TCP/IP: Windows NT 4.0 Does Not Support TCP Scale Option [Q199947]">MS KB199947</a>

 To configure Max number of Duplicate Acknowledgments (ACK's) (WinNT4 Requires SP2):
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  TcpMaxDupAcks = 2 (Range 1-3, Default = 2)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+162179+Q162179" rel="nofollow" title="TCP Fast Retransmit and Recovery Added in Windows NT 4.0 Service Pack 2 [Q162179]">MS KB162179</a>

 Note none of these registry entries can be found in the registry after a clean install, so to return to the default values just delete the registry entries.  
  
 Related [Delayed TCPIP ACK can cause slow network throughput](/article/winnt-nagle-algorithm.html)  
 Related [Configure the max limit for concurrent TCP connections](/article/winnt-tcpip-max-limit.html)  
  
 More articles about the settings available for configuring the tcpip stack: - <a href="https://www.bing.com/search?q=KB+140552+Q140552" rel="nofollow" title="How to Optimize Windows NT to Run Over Slow WAN Links w/TCP/IP [Q140552]">MS KB140552</a> - Minimize traffic over WAN.
- <a href="https://www.bing.com/search?q=KB+819108+Q819108" rel="nofollow" title="Settings for minimizing periodic WAN traffic [Q819108]">MS KB819108</a> - Minimize traffic over WAN.
- <a href="https://www.bing.com/search?q=KB+900926+Q900926" rel="nofollow" title="Recommended TCP/IP settings for WAN links with a MTU size of less than 576 [Q900926]">MS KB900926</a> - Using WAN with MTU less than 576
- <a href="https://www.bing.com/search?q=KB+120642+Q120642" rel="nofollow" title="TCP/IP and NetBT configuration parameters for Windows 2000 or Windows NT [Q120642]">MS KB120642</a> - TCP/IP &amp; NBT Configuration Parameters for Windows NT and Windows 2000
- <a href="https://www.bing.com/search?q=KB+224829+Q224829" rel="nofollow" title="Description of Windows 2000 and Windows Server 2003 TCP Features [Q224829]">MS KB224829</a> - Description of Windows 2000 and Windows Server 2003 TCP Features
- <a href="https://www.bing.com/search?q=KB+314053+Q314053" rel="nofollow" title="TCP/IP and NBT Configuration Parameters for Windows XP [Q314053]">MS KB314053</a> - TCP/IP and NBT Configuration Parameters for Windows XP
- <a href="https://www.bing.com/search?q=KB+142641+Q142641" rel="nofollow" title="Internet server unavailable because of malicious SYN attacks [Q142641]">MS KB142641</a> - Internet Server Unavailable Because of Malicious SYN Attacks
- <a href="https://www.bing.com/search?q=KB+315669+Q315669" rel="nofollow" title="How to harden the TCP/IP stack against denial of service attacks in Windows 2000 [Q315669]">MS KB315669</a> - HOW TO: Harden the TCP/IP Stack Against Denial of Service Attacks in Windows 2000
- <a href="https://www.bing.com/search?q=KB+324270+Q324270" rel="nofollow" title="How to harden the TCP/IP stack against denial of service attacks in Windows Server 2003 [Q324270]">MS KB324270</a> - HOW TO: Harden the TCP/IP Stack Against Denial of Service Attacks in Windows Server 2003
- [MS Technet](http://www.microsoft.com/technet/itsolutions/network/deploy/depovg/tcpip2k.mspx) - Microsoft Windows 2000 TCP/IP Implementation Details [Word Document](http://www.microsoft.com/windows2000/techinfo/howitworks/communications/networkbasics/tcpip_implement.asp)
- [MS Technet](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/networking/tcpip03.mspx) - Microsoft Windows Server 2003 TCP/IP Implementation Details
- [MS Technet](http://www.microsoft.com/technet/archive/security/prodtech/windows/iis/dosrv.mspx) - Security Considerations for Network Attacks
- [MS Technet](https://www.microsoft.com/technet/interopmigration/unix/sfu/perfnfs.mspx) - Performance Tuning Guidelines for Microsoft Services for Network File System
- [TCPIMP2.EXE &amp; TCPIPIMP.EXE](ftp://ftp.microsoft.com/bussys/winnt/winnt-docs/papers/) - WinNT TCPIP Whitepapers [Mirror](http://www.microsoft.com/ntserver/docs/TCPIP.DOC)
 
 Credits [regedit.com](http://registry.winguides.com/display.php/645/)  