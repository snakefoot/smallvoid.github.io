---
title: 'Configure the max limit for concurrent TCP connections'
date: '2004-03-06T00:54:59+01:00'
permalink: /article/winnt-tcpip-max-limit.html
author: Snakefoot
excerpt: 'Windows is configured by default to handle 1000 to 2000 concurrent tcpip connections.'
type: post
id: 434
categories:
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - crippled
    - ephemeral
    - tcpip
---
To keep the TCP/IP stack from taking all resources on the computer, there are different parameters that control how many connections it can handle. If running applications that are constantly opening and closing connections (P2P), or are providing a service which many tries to connect to at the same time (Web-server like IIS), then one can improve the performance of these applications by changing the restriction limits.  
  
 There is a parameter that limits the maximum number of connections that TCP may have open simultaneously.

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  TcpNumConnections = 0x00fffffe (Default = 16,777,214)  
>   
>  Note a 16 Million connection limit sounds very promising, but there are other parameters (See below), which keeps us from ever reaching this limit.

 When a client makes a connect() call to make a connection to a server, then the client invisible/implicit bind the socket to a local dynamic (anonymous, ephemeral, short-lived) port number. The default range for dynamic ports in Windows is 1024 to 5000, thus giving 3977 outbound concurrent connections for each IP Address. It is possible to change the upper limit with this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  MaxUserPort = 5000 (Default = 5000, Max = 65534)  
>   
>  Note it is possible to reserve port numbers so they aren't used as dynamic ports in case one have a certain application that needs them. This is done by using the <a href="https://www.bing.com/search?q=KB+812873+Q812873" title="How to Reserve a Range of Ephemeral Ports on a Computer Running Windows 2000 [Q812873]" rel="nofollow">ReservedPorts (MS KB812873)</a> setting.  
>   
>  Note Vista changes the default range from 1024-5000 to 49152-65535, which can be controlled with the dynamicport setting using netsh. More Info <a href="https://www.bing.com/search?q=KB+929851+Q929851" rel="nofollow" title="The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008">MS KB929851</a>.  
>   
>  More Info [The Cable Guy - Ephemeral, Reserved, and Blocked Port Behavior](http://www.microsoft.com/technet/community/columns/cableguy/cg1205.mspx)  
>  More Info <a href="https://www.bing.com/search?q=KB+196271+Q196271" rel="nofollow" title="Unable to Connect from TCP Ports Above 5000 [Q196271]">MS KB196271</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+319502+Q319502" rel="nofollow" title="PRB: WSAEADDRESSINUSE Error Message When You Try to Connect Through an Anonymous Port After You Increase the IMAP Connection Limit [Q319502]">MS KB319502</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+319504+Q319504" rel="nofollow" title="Error Message: The Name Limit for the Local Computer Network Adapter Card Was Exceeded [Q319504]">MS KB319504</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+328476+Q328476" rel="nofollow" title="TCP/IP Settings for SQL Server Drivers When Pooling Is Disabled [Q328476]">MS KB328476</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+836429+Q836429" rel="nofollow" title="'The server is not operational' message in the Migration.log file when you use the ADMT Ver.2 in Win2k3 or in Win2k [Q836429]">MS KB836429</a>

 For each connection a TCP Control Block (TCB - Data structure using 0.5 KB [pagepool](/article/winnt-kernel-memory.html) and 0.5 KB non-pagepool) is maintained. The TCBs are pre-allocated and stored in a table, to avoid spending time on allocating/deallocating the TCBs every time connections are created/closed. The TCB Table enables reuse/caching of TCBs and improves memory management, but the static size limits how many connections TCP can support simultaneously (Active + TIME\_WAIT). Configure the size of the TCB Table with this DWORD registry key:
 > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
 >  MaxFreeTcbs = 2000 (Default = RAM dependent, but usual Pro = 1000, Srv=2000)

 To make lookups in the TCB table faster a hash table has been made, which is optimized for finding a certain active connection. If the hash table is too small compared to the total amount of active connections, then extra CPU time is required to find a connection. Configure the size of the hash table with this DWORD registry key (Is allocated from pagepool memory):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\services \\Tcpip \\Parameters\]  
>  MaxHashTableSize = 512 (Default = 512, Range = 64-65536)  
>   
>  Note Microsoft recommends for a multiprocessor environment, that the value should not be higher than the maximum amount of concurrent connections (MaxFreeTcbs), also if multiprocessor then it might be interesting to look at the registry-key NumTcbTablePartitions (Recommended value CPU-count multiplied by 4).  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+151418+Q151418" rel="nofollow" title="WinNT TCP/IP May Reuse TIME-WAIT Connections Prior to 2MSL [Q151418]">MS KB151418</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+224585+Q224585" rel="nofollow" title="TCB Hash Function Modified to Improve Network Performance [Q224585]">MS KB224585</a>

 If having allocated a 1000 TCBs then it doesn't mean that one will be able to have a 1000 active connections. Especially if the application is quickly opening and closing connections, because after a connection is "closed" it enters the state TIME\_WAIT, and will continue to occupy the port number for 4 minutes (2\*Maximum Segment Live, MSL) before it is actually removed. This behavior is specified in [RFC 793](http://www.faqs.org/rfcs/rfc793.html), and prevents attempts to reconnect to the same party, before the old socket is recognized as closed at both sides. It is possible to change how long a socket should be in TIME\_WAIT state before it can be re-used freely:
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\services \\Tcpip \\Parameters\]  
>  TcpTimedWaitDelay = 120 (Default = 240 secs, Range = 30-300)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+137984+Q137984" rel="nofollow" title="TCP Connection States and Netstat Output [Q137984]">MS KB137984</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+149532+Q149532" rel="nofollow" title="Windows NT Clients Run Out of Ports [Q149532]">MS KB149532</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+832954+Q832954" rel="nofollow" title="A Windows Rights Management Services (RMS) server may not service all requests [Q832954]">MS KB832954</a>  
>   
>  Note with Win2k the reuse of sockets have been changed, so when reaching the limit of more than 1000 connections in TIME-WAIT state, then it starts to mark sockets that have been in TIME\_WAIT state for more than 60 secs as free. It is possible to configure this limit:  
>   
>  \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\services \\Tcpip \\Parameters\]  
>  MaxFreeTWTcbs = 1000 (Default = 1000 sockets)  
>   
>  Note with Win2k3 SP1 the reuse of sockets have been changed, so when it has to re-use sockets in TIME\_WAIT state, then it checks whether the other party is different from the old socket. Eliminating the need to fiddle with (TcpTimedWaitDelay) and (MaxFreeTWTcbs) any more.

 If using an application protocol that doesn't implement timeout checking, but relies on the TCPIP timeout checking without specifying how often it should be done, then it is possible to get connections that "never" closes, if the remote host disconnects without closing the connection properly. The TCPIP timeout checking is by default done every 2 hour, by sending a keep alive packet. It is possible to change how often TCPIP should check the connections (Affects all TCPIP connections):
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\services \\Tcpip \\Parameters\]  
>  KeepAliveTime = 1800000 (Default = 7,200,000 milisecs)  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+140325+Q140325" rel="nofollow" title="How to Determine Loss of Client/Server Connection [Q140325]">MS KB140325</a>

 When data is sent/received the data is copied back and forth to [non-paged pool memory](/article/winnt-kernel-memory.html) for buffering. If there are many connections receiving/sending data, then it is possible to exhaust the non-paged pool memory. The max size of the non-paged pool buffer allocated for each connection is controlled by MaxBufferredReceiveBytes or [TCPIP Receive Window](/article/tcpip-rwin-size.html) depending on which is smallest. More Info <a href="https://www.bing.com/search?q=KB+296265+Q296265" rel="nofollow" title="Windows 2000 Non-Paged Pool Is Exhausted by Afd.sys [Q296265]">MS KB296265</a>  
  
 Note if using the Professional/Home edition of Windows then it is very likely that it is crippled (By Microsoft) not to handle many concurrent TCP connections. Ex. Microsoft have officially stated that the backlog limit is 5 (200 when Server), so the Professional edition is not able to accept() more than 5 new connections concurrently. More Info <a href="https://www.bing.com/search?q=KB+127144+Q127144" rel="nofollow" title="Windows NT WinSock Listen (Backlog) Parameter Limit [Q127144]">MS KB127144</a>  
  
 Note even if having optimized Windows to handle many concurrent connections, then connections might still be refused when reaching a certain limit, in case a NAT-Router/Firewall is placed infront of it, which is unable to handle so many concurrent connections.  
  
 Note if having activated <a href="https://www.bing.com/search?q=KB+324270+Q324270" title="How to harden the TCP/IP stack against denial of service attacks in Windows Server 2003 [Q324270]" rel="nofollow">SYN-Attack-Protection</a> (Enabled by default in Win2k3 SP1) or installed WinXP SP2, a limit is introduced on how many connection attempts (half-open) one can make simultaneously (XP SP2 &amp; Vista = 10; Vista SP2 = no limit). This will keep worms like [blaster](/article/winnt-blaster-rpc-exploit.html) and [sasser](/article/winnt-sasser-lsa-exploit.html) from spreading too fast, but it will also limit other applications that creates many new connections simultaneously (Like P2P).
> *EventID 4226: TCP/IP has reached the security limit imposed on the number of concurrent TCP connect attempts*  
>   
>  More Info [www.LvlLord.de](http://www.lvllord.de/)  
>   
>  Windows Vista SP2 removes the limit again, but it can be enabled with the following DWORD registry setting:  
>   
>  \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Tcpip \\Parameters\]  
>  EnableConnectionRateLimiting = 1  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+969710+Q969710" rel="nofollow" title="How to enable the half-open TCP connections limit in Windows Vista with SP2">MS KB969710</a>

 Related [No more than 10 connections to a remote computer](/article/winnt-network-connection-limit.html)