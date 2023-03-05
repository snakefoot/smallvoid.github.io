---
title: 'Using TCP/IP Version 6 (IPv6) can make network slow'
date: '2006-02-01T01:06:43+01:00'
status: publish
permalink: /article/winnt-ipv6-dns-error.html
author: Snakefoot
excerpt: 'Before activating TCP/IP Version 6 then one should make sure that the DNS server is able to handle IPv6 properly.'
type: post
id: 435
category:
    - Network
    - Network
    - Network
tag:
    - dns
    - ipv6
    - lan
    - tcpip
    - wan
post_format: []
tags:
    - 'ipv6,dns,tcpip,lan,wan'
---
Internet Procotol ver. 6 (IPv6) contains many new improvements:

- 128 bit address space (IPv4 uses 32 bit)
- Easier configuration (IPv4 uses DHCP or manual setting static IP address)
- Built-in security
- Better support for Quality of Service (QoS)
 
 Sadly enough not all Internet Service Providers (ISP) are able to handle IPv6 properly. For example some IPv4 DNS servers cannot handle IPv6 "AAAA"-record lookup requests. Instead of replying NOERROR and an empty reply, then they respond NXDOMAIN or NAME\_ERROR or not responding at all. This either causes very slow DNS lookups because of timeouts or failure to perform the DNS lookup at all.  
  
##### To uninstall IPv6 (And only use IPv4) in WinXP:

1. Open **Control Panel** -&gt; **Network Connection**
2. Right Click the network interface card, and select **Properties**.
3. Select IPv6 and press **Uninstall**
  - Vista/Win7 cannot uninstall IPv6 but clearing the checkbox for IPv6 will disable it for the network connection. More Info [MS KB929852](http://support.microsoft.com/kb/929852 "How to disable certain Internet Protocol version 6 (IPv6) components")
4. Restart
 
 More Info [MS KB325449](http://support.microsoft.com/kb/325449 "How to install and configure IP version 6 in Windows Server 2003 Enterprise Server [Q325449]")  
 More Info [MS KB815768](http://support.microsoft.com/kb/815768 "Application Cannot Resolve Some Domain Names")  
 More Info [MS KB817778](http://support.microsoft.com/kb/817778 "Overview of the Advanced Networking Pack for Windows XP")  