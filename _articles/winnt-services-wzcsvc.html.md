---
title: 'Wireless Zero Configuration (WZC)'
date: '2000-07-23T23:47:10+02:00'
permalink: /article/winnt-services-wzcsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Wireless Zero Configuration service.'
type: post
id: 624
categories:
    - windows-2000_services
    - windows-2003_services
    - windows-xp_services
tags:
    - wep
    - wifi
    - wireless-network
    - wlan
    - wpa
---
##### Description:

 Provides automatic configuration for the 802.11 adapters.  
  
 The IEEE 802.11 standard specifies optional security improvements for wireless local area networking:
- Authentication using 802.1x to avoid being vulnerable to attacks such as offline traffic analysis, bit flipping, and malicious packet injection
- Key Management with rekeying of unicast encryption keys
- Temporal Key Integrity Protocol (TKIP) uses Wired Equivalent Privacy (WEP) for encryption
 
 The [Wi-Fi Protected Access (WPA)](http://www.wifialliance.org/) is an extension to the IEEE 802.11 standard:
- 802.1x authentication is not optional
- Key Management provides rekeying of both unicast and global encryption keys and is not optional
- Temporal Key Integrity Protocol (TKIP) replaces WEP with a stronger encryption algorithm and is not optional
 
 Note many times the manufactures of wireless network adapters provides a wireless-client specifically made for their wireless adapter. Usually it is better to use the manufactures wireless-client instead this one from Microsoft. Especially since it has been reported that Microsoft wireless-client routinely drops the WIFI connection when having disabled SSID broadcasts, More Info <a href="https://www.bing.com/search?q=KB%20811427%20Q811427" rel="nofollow" title="Your Computer Connects to an Access Point That Broadcasts Its SSID Instead of an Access Point That Does Not Broadcast its SSID [Q811427]">MS KB811427</a>, or if having checked 'Enable IEEE 802.1x authentication for this network', More Info <a href="https://www.bing.com/search?q=KB%20814123%20Q814123" rel="nofollow" title="MSBBN: Wireless Network Connection Drops Every Few Minutes [Q814123]">MS KB814123</a>.  
  
 Note the Wireless Zero Configuration (WZC) service uses NDIS User Mode I/O (NDISUIO) NDIS protocol driver to query and monitor network adapters (Ethernet, WLAN etc.). Therefore some software firewall will report activity from the NDISUIO.SYS when using the WZC service, but it is perfectly harmless.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20314897%20Q314897" rel="nofollow" title="HOW TO: Enable Windows XP Automatic Wireless Network Configuration [Q314897]">MS KB314897</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20318710%20Q318710" rel="nofollow" title="HOW TO: Support Wireless Connections in Windows 2000 [Q318710]">MS KB318710</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20328601%20Q328601" rel="nofollow" title="INFO: Capturing Debug and Diagnostic Logging from WZC for Wireless NICs [Q328601]">MS KB328601</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20815485%20Q815485" rel="nofollow" title="Overview of the WPA Wireless Security Update in Windows XP [Q815485]">MS KB815485</a> <a href="https://www.bing.com/search?q=KB%20826942%20Q826942" rel="nofollow" title="Wireless Update Rollup Package for Windows XP is Available [Q826942]">MS KB826942</a> (WPA for WinXP SP1)  
 More Info <a href="https://www.bing.com/search?q=KB%20831749%20Q831749" rel="nofollow" title="Support WebCast: How to Set Up and Improve the Security of Home Wireless Networks [Q831749]">MS KB831749</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20870702%20Q870702" rel="nofollow" title="How to troubleshoot wireless network connections in Windows XP Service Pack 2 [Q870702]">MS KB870702</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20894568%20Q894568" rel="nofollow" title="How to gather information to troubleshoot a wireless connectivity problem in Windows XP [Q894568]">MS KB894568</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20917021%20Q917021" rel="nofollow" title="Description of the Wireless Client Update for Windows XP with Service Pack 2 [Q917021]">MS KB917021</a> (WPA2 for WinXP SP2)  
 More Info [WSC WPA Assistant for Win2k](http://www.wirelesssecuritycorp.com/wsc/public/WPAAssistant.do "Wireless Security Corporation") (Freeware with security "reminders")  
  
##### Recommended State:

- Disabled, if not using wireless network with a 802.11 network device.
- Automatic, if using wireless netwok AND manufacture of the netcard haven't provided software of their own.

##### Default State:

- Win2k SP4+: Manual.
- WinXP: Automatic.
- Win2k3 Std./Enterprise/Datacenter: Automatic.
- Win2k3 Web: Manual.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (WZCSVC)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Protected Storage](/article/winnt-services-protectedstorage.html) (Win2k SP4+ Only)
- [Windows Management Instrumentation Driver Extensions](/article/winnt-services-wmi.html) (Win2k SP4+ Only)