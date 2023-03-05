---
title: 'Windows XP firewall log reader'
date: '2003-08-18T17:51:56+02:00'
status: publish
permalink: /article/winxp-firewall-log.html
author: Snakefoot
excerpt: 'Windows XP firewall log can be used to monitor those who are trying to access the computer.'
type: post
id: 513
category:
    - Utilities
tag:
    - firewall
    - security
post_format: []
tags:
    - 'firewall,security'
---
The following utilities can be used to read the log created by the firewall builtin Windows XP:

- [XP Firewall LogReader](http://www.majorgeeks.com/download.php?det=3307 "Mindthought.com: XP Firewall Log Reader by mcbweb")
- [FireLogXP](http://www.2brightsparks.com/freeware/freeware-hub.html "www.mjleaver.com")
 
 WinXP's Internet Connection Firewall (ICF) can be configured to save warnings to a log:
1. Open **Control Panel** and double click **Network and Internet Connections** and open **Network Connections**.
2. Click the connection on which Internet Connection Firewall (ICF) is enabled, and then, under **Network Tasks**, click **Change settings of this connection**.
3. On the **Advanced**-tab, click **Settings**.
4. On the **Security Logging**-tab, under **Logging Options**, select one or both of the following options: 
  - To enable logging of unsuccessful inbound connection attempts, select the **Log dropped packets** check box.
  - To enable logging of successful outbound connections, select the **Log successful connections** check box.
 
 By using an utility to read this log, then it becomes easier to see who is attacking, and troubleshoot why a certain application is not connecting properly to the Internet.  
  
 More Info [Internet Connection Firewall security log file overview](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/hnw_firewall_log_understanding.mspx)  
  
 Related [Setting up WinXP Internet Connection Firewall (ICF)](/article/winxp-firewall.html)