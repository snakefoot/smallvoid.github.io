---
title: 'Setting up an Internet Connection Firewall (ICF)'
date: '2002-05-10T00:17:58+02:00'
status: publish
permalink: /article/winxp-firewall.html
author: Snakefoot
excerpt: 'How to configure the Windows XP firewall rules for incoming connections.'
type: post
id: 429
category:
    - Network
tag:
    - firewall
    - internet
    - port-forwarding
post_format: []
tags:
    - 'firewall,internet,port-forwarding'
---
Microsoft provides a simple firewall in Windows XP that protects from incoming traffic, but it will not block for outgoing traffic maybe caused by a virus that have taken over the computer. Windows XP SP2 includes an updated firewall, which still doesn't block for outgoing traffic, but it gives a better interface for controlling incoming traffic (File Sharing, Games, etc.)  
  
 Technet articles for XP SP2:

- [How to script netsh to configure Windows Firewall features in Windows XP Service Pack 2 (MS KB843090)](http://support.microsoft.com/kb/839980)
- [Description of the Windows Firewall feature in Windows XP Service Pack 2 (MS KB843090)](http://support.microsoft.com/kb/843090)
- [How to configure the Windows Firewall feature in Windows XP Service Pack 2 (MS KB875356)](http://support.microsoft.com/kb/875356)
- [Troubleshooting Windows Firewall settings in Windows XP Service Pack 2 (MS KB875357)](http://support.microsoft.com/kb/875357)
 
 Technet articles for XP and XP with Service Pack 1: - [Description of the Windows XP Internet Connection Firewall (MS KB320855)](http://support.microsoft.com/kb/320855)
- [Description of a Personal Firewall (MS KB321050)](http://support.microsoft.com/kb/321050)
- [HOW TO: Enable or Disable Internet Connection Firewall in Windows XP (MS KB283673)](http://support.microsoft.com/kb/283673)
- [HOW TO: Determine Which Program Uses or Blocks Specific Transmission Control Protocol Ports in Windows (MS KB281336)](http://support.microsoft.com/kb/281336)
- [Service redirection does not apply to Internet Connection Firewall (MS KB297942)](http://support.microsoft.com/kb/297942)
- [The Internet Connection Firewall Can Prevent Browsing and File Sharing (MS KB298804)](http://support.microsoft.com/kb/298804)
- [How to Manually Open Ports in Internet Connection Firewall in Windows XP (MS KB308127)](http://support.microsoft.com/kb/308127)
- [HOW TO: Turn On the Internet Connection Firewall Feature in Windows Server 2003 (MS KB317530)](http://support.microsoft.com/kb/317530)
 
 To configure if the WinXP SP1 firewall should allow ping:
1. In Control Panel double click "Networking and Internet Connections"
2. Right click the connection which you would like to get pinged, and select "Properties"
3. On the Advanced-tab press the Settings-button
4. On the ICMP-tab tick "Allow incoming echo request"