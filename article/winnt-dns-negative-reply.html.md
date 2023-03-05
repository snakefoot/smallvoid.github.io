---
title: 'Configure how long to cache negative DNS replies'
date: '2003-04-07T00:38:16+02:00'
status: publish
permalink: /article/winnt-dns-negative-reply.html
author: Snakefoot
excerpt: 'By not caching negative DNS lookups then one will quickly recover in case a domain is unregistered and registered again.'
type: post
id: 433
category:
    - Network
    - Network
    - Network
tag:
    - address-resolution-protocol
    - dns
    - name-resolution
post_format: []
tags:
    - 'dns,address-resolution-protocol,name-resolution'
---
When accessing a domain like www.google.com it first has to convert the domain to an IP Address. This [domain resolution](/article/windows-host-name-resolution.html) is performed by sending the domain to a DNS server which replies back with the IP Address. This conversion can be seen when pinging a domain.  
  
 With Windows 2000 the [DNS Client](/article/winnt-services-dnscache.html) caches the DNS lookups, so it doesn't have to spend time on contacting the DNS Server all the time, and decreases the traffic to the DNS server. But negative DNS replies are also cached and used for up to 15 min before it again requests the DNS Server. This waiting time can be annoying if the domain is correct and the DNS Server just were sick for a moment. The waiting time can be configured with these DWORD values:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Dnscache \\Parameters\]  
>  NegativeCacheTime = 5 (Win2k Default 300 sec)  
>  MaxNegativeCacheTtl = 5 (WinXP/Win2k3 Default 900 sec)

 Note using 5 sec instead of 0 sec to throttle the requests to the DNS Server in case a faulty application loops around a DNS Lookup.  
  
 Note to see the contents of the DNS cache:
 > ipconfig /displaydns

 Note to empty/flush/reset the DNS cache manually ([Part of WinXP Network Repair](http://support.microsoft.com/kb/289256 "A Description of the Repair Option on a Local Area Network or High-Speed Internet Connection [Q289256]")):
 > ipconfig /flushdns

 Note to flush the Address Resolution Protocol (ARP) cache of Ethernet Addresses ([Part of WinXP Network Repair](http://support.microsoft.com/kb/289256 "A Description of the Repair Option on a Local Area Network or High-Speed Internet Connection [Q289256]")):
 > arp -d \*  
 > netsh interface ip delete arpcache

 Note to purge and reload the NetBIOS cache ([Part of WinXP Network Repair](http://support.microsoft.com/kb/289256 "A Description of the Repair Option on a Local Area Network or High-Speed Internet Connection [Q289256]")):
 > nbtstat -R

 More Info [MS KB245437](http://support.microsoft.com/kb/245437 "How to Disable Client-Side DNS Caching in Windows [Q245437]")  
 More Info [MS KB297510](http://support.microsoft.com/kb/297510 "HOW TO: Modify Time to Live on Domain Name System Records [Q297510]")  
 More Info [MS KB318803](http://support.microsoft.com/kb/318803 "How to Disable Client-Side DNS Caching in Windows XP and Windows Server 2003 [Q318803]")  
  
 Related [Microsoft TCP/IP Version 6 (IPv6) can cause slow DNS](/article/winnt-ipv6-dns-error.html)  
  
 Credits [Navas Cable Guide](http://cable-dsl.home.att.net/)