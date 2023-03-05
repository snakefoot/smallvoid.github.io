---
title: 'DNS Client'
date: '2000-07-23T01:33:53+02:00'
status: publish
permalink: /article/winnt-services-dnscache.html
author: Snakefoot
excerpt: 'Description and recommended settings for the DNS Client service.'
type: post
id: 542
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dns
    - hosts-file
    - name-resolution
    - tcpip
post_format: []
tags:
    - 'dns,name-resolution,tcpip,hosts-file'
---
##### Description:

 The DNS Client acts like a local DNS server, and is used whenever an application requires to resolve a Domain Name System (DNS) name.  
  
 If an application wants to connect to www.google.com, then it requests the DNS client for it to convert it to an IP address. If the DNS client doesn't recognize the domain it passes the request to the network DNS Server (Port 53), but caches the reply for later use by the same or other applications and thus increases the speed of future DNS lookups and causes less load on the network DNS Server.  
  
 When using WinXP to logon to a domain one should register the domain server's IP as the primary DNS Server. If this is not done the login to the domain will be very slow.  
  
 When using Win2k/WinXP to [logon to a WinNT4 domain](http://support.microsoft.com/kb/810497 "Check-List for solving logon troubles [Q810497]") one should enable Netbios over TCP/IP for the Internet Protocol in network properties on Win2k/WinXP as the WinNT4 domain doesn't use DNS.  
  
 Note if using a large [HOSTS file to ban ads](/article/windows-hosts-file.html), then it will lead to slow performance when having the DNS Client enabled. To avoid the slowdown, then one either has to disable the DNS Client or avoid using a large HOSTS file.  
  
 Note in Windows XP this service keeps the same UDP connection open to make all DNS requests. In Windows 2000 the service opens/closes a UDP connection for each request. To make XP behave like Windows 2000 use this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\Dnscache \\Parameters\]  
>  MaxCachedSockets = 0

 Note if having disabled this service, and then try to repair a network connection, one will get the following error message:
> *The following steps of the repair operation failed: Purging the DNS Resolver Cache. Please contact your network administrator or ISP.*   
>   
> More Info [MS KB913631](http://support.microsoft.com/kb/913631 "Error message that is similar to the following when you use the Repair option for a local area connection in Windows XP: "The following steps of the repair operation failed" [Q913631]")

 Related [Configure how long to cache negative DNS replies](/article/winnt-dns-negative-reply.html)  
 Related [Microsoft TCP/IP Version 6 (IPv6) can cause slow DNS](/article/winnt-ipv6-dns-error.html)  
 Related [Configure the host name resolution order](/article/winnt-host-name-resolution.html)  
 Related [Use HOSTS file to ban ads and speedup DNS lookups](/article/windows-hosts-file.html)  
  
 More Info [MS KB286834](http://support.microsoft.com/kb/286834 "The DNS Client Service Does Not Revert to Using the First Server in the List [Q286834]")  
 More Info [MS KB264539](http://support.microsoft.com/kb/264539 "Dynamic DNS Updates Do Not Work if the DHCP Client Service Stops [Q264539]")  
 More Info [MS KB268674](http://support.microsoft.com/kb/268674 "No DNS Name Resolution If DHCP Client Service Is Not Running [Q268674]")  
 More Info [MS KB245437](http://support.microsoft.com/kb/245437 "How to Disable Client-Side DNS Caching in Windows [Q245437]")  
 More Info [MS KB246804](http://support.microsoft.com/kb/246804 "How to Enable/Disable Windows 2000 Dynamic DNS Registrations [Q246804]")  
 More Info [MS KB294832](http://support.microsoft.com/kb/294832 "How to Disable Windows 2000 Dynamic Domain Name System Registrations with Group Policy [Q294832]")  
 More Info [MS KB320760](http://support.microsoft.com/kb/320760 "The DNS Client Service Does Not Revert to Using the First Server in the List in Windows XP [Q320760]")  
  
##### Recommended State:

- Automatic, to minimize network traffic for the cost of memory.
- Disabled, if not wanting to have DNS caching and want every application to do their own DNS lookup.

##### Default State:

- Win8: Automatic (Trigger Start - FIREWALL PORT EVENT)
- Win7/Vista/WinXP/Win2k3/Win2k: Automatic

##### Process Name:

- Win8/Win7/Vista/WinXP/Win2k3: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (Dnscache)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Dnscache)

##### Supports:

- [Network Connectivity Assistant](/article/winnt-services-ncasvc.html) (Win8+)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html) (Win7+)