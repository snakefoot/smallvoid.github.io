---
title: 'Using TCP/IP Version 6 (IPv6) can make network slow'
date: '2006-02-01T01:06:43+01:00'
permalink: /article/winnt-ipv6-dns-error.html
author: Snakefoot
excerpt: 'Before activating TCP/IP Version 6 then one should make sure that the DNS server is able to handle IPv6 properly.'
type: post
id: 435
categories:
    - windows-xp_network
    - windows-2003_network
    - windows-vista_network
tags:
    - dns
    - ipv6
    - lan
    - tcpip
    - wan
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
  - Vista/Win7 cannot uninstall IPv6 but clearing the checkbox for IPv6 will disable it for the network connection. More Info <a href="https://www.bing.com/search?q=KB+929852+Q929852" rel="nofollow" title="How to disable certain Internet Protocol version 6 (IPv6) components">MS KB929852</a>
4. Restart
 
 More Info <a href="https://www.bing.com/search?q=KB+325449+Q325449" rel="nofollow" title="How to install and configure IP version 6 in Windows Server 2003 Enterprise Server [Q325449]">MS KB325449</a>  
 More Info <a href="https://www.bing.com/search?q=KB+815768+Q815768" rel="nofollow" title="Application Cannot Resolve Some Domain Names">MS KB815768</a>  
 More Info <a href="https://www.bing.com/search?q=KB+817778+Q817778" rel="nofollow" title="Overview of the Advanced Networking Pack for Windows XP">MS KB817778</a>  