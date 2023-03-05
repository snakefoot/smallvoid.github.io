---
title: 'DHCP Client'
date: '2000-07-23T00:50:25+02:00'
status: publish
permalink: /article/winnt-services-dhcp.html
author: Snakefoot
excerpt: 'Description and recommended settings for the DHCP Client service.'
type: post
id: 535
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dhcp
post_format: []
tags:
    - dhcp
---
##### Description:

 DHCP(Dynamic Host Configuration Protocol) is used to store network configuration at a central place (DHCP Server). The DHCP client will automatically contact the DHCP server (Port 67) and acquire what network configuration it should use. - Client IP-Address
- Gateway IP-Address
- Primary &amp; Secondary DNS Server IP-Addresses
 
 Note if the computer is part of a domain and dynamic DNS (DDNS) is used, then one should be aware that the DHCP Client is also responsible for registering the computer in the DNS.  
  
 Note if the client is configured in the network properties to acquire its TCPIP configuration through TCPIP, and there is no DHCP-Server available to serve an IP-Address to the client, then the client will block while timing out.  
  
 Note if the DHCP Client service is disabled or cannot find a DHCP server (not able to ping, [broken TCPIP stack](/article/winnt-netsh.html)), then the command "ipconfig /renew" will give the following error message:
 > *An error has occurred while renewing interface Local Area Connection. The RPC server is unavailable.*

 More Info [Microsoft DHCP](http://www.microsoft.com/dhcp/)  
  
 Related [Automatic TCP/IP addressing when DHCP fails to respond](/article/automatic-tcpip-addressing.html)  
 Related [Using static TCP/IP-Address makes the boot time faster](/article/dhcp-static-ip.html)  
 Related [DHCP fails when using broadcast request](/article/vista-dhcp-client-broadcast.html)/&gt;   
##### Recommended State:

- Automatic, if using dynamic IP and on network with a DHCP server (Ex. Dialup user).
- Disabled, if using a static IP (And the computer doesn't need to register its hostname in DNS).

##### Default State:

- Automatic

##### Process Name:

- Win8/Win7/Vista: [svchost.exe -k LocalServiceNetworkRestricted](/article/winnt-services-wrapper.html) (Dhcp)
- WinXP: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Dhcp)
- Win2k3: [svchost.exe -k NetworkService](/article/winnt-services-wrapper.html) (Dhcp)
- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Dhcp)

##### Supports:

- [WinHTTP Web Proxy Auto-Discovery Service](/article/winnt-services-nla.html) (Win2k3+)
- [Network Location Awareness](/article/winnt-services-winhttpautoproxysvc.html) (Win8+)

##### Depends:

- [Network Store Interface Service](/article/winnt-services-nsi.html) (Vista+)