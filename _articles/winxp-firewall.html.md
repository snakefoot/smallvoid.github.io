---
title: 'Setting up an Internet Connection Firewall (ICF)'
date: '2002-05-10T00:17:58+02:00'
permalink: /article/winxp-firewall.html
author: Snakefoot
excerpt: 'How to configure the Windows XP firewall rules for incoming connections.'
type: post
id: 429
categories:
    - windows-xp_network
tags:
    - firewall
    - internet
    - port-forwarding
---
Microsoft provides a simple firewall in Windows XP that protects from incoming traffic, but it will not block for outgoing traffic maybe caused by a virus that have taken over the computer. Windows XP SP2 includes an updated firewall, which still doesn't block for outgoing traffic, but it gives a better interface for controlling incoming traffic (File Sharing, Games, etc.)  
  
 Technet articles for XP SP2:

- <a href="https://www.bing.com/search?q=KB+843090+Q843090" rel="nofollow">How to script netsh to configure Windows Firewall features in Windows XP Service Pack 2 (MS KB843090)</a>
- <a href="https://www.bing.com/search?q=KB+843090+Q843090" rel="nofollow">Description of the Windows Firewall feature in Windows XP Service Pack 2 (MS KB843090)</a>
- <a href="https://www.bing.com/search?q=KB+875356+Q875356" rel="nofollow">How to configure the Windows Firewall feature in Windows XP Service Pack 2 (MS KB875356)</a>
- <a href="https://www.bing.com/search?q=KB+875357+Q875357" rel="nofollow">Troubleshooting Windows Firewall settings in Windows XP Service Pack 2 (MS KB875357)</a>
 
 Technet articles for XP and XP with Service Pack 1:
- <a href="https://www.bing.com/search?q=KB+320855+Q320855" rel="nofollow">Description of the Windows XP Internet Connection Firewall (MS KB320855)</a>
- <a href="https://www.bing.com/search?q=KB+321050+Q321050" rel="nofollow">Description of a Personal Firewall (MS KB321050)</a>
- <a href="https://www.bing.com/search?q=KB+283673+Q283673" rel="nofollow">HOW TO: Enable or Disable Internet Connection Firewall in Windows XP (MS KB283673)</a>
- <a href="https://www.bing.com/search?q=KB+281336+Q281336" rel="nofollow">HOW TO: Determine Which Program Uses or Blocks Specific Transmission Control Protocol Ports in Windows (MS KB281336)</a>
- <a href="https://www.bing.com/search?q=KB+297942+Q297942" rel="nofollow">Service redirection does not apply to Internet Connection Firewall (MS KB297942)</a>
- <a href="https://www.bing.com/search?q=KB+298804+Q298804" rel="nofollow">The Internet Connection Firewall Can Prevent Browsing and File Sharing (MS KB298804)</a>
- <a href="https://www.bing.com/search?q=KB+308127+Q308127" rel="nofollow">How to Manually Open Ports in Internet Connection Firewall in Windows XP (MS KB308127)</a>
- <a href="https://www.bing.com/search?q=KB+317530+Q317530" rel="nofollow">HOW TO: Turn On the Internet Connection Firewall Feature in Windows Server 2003 (MS KB317530)</a>
 
 To configure if the WinXP SP1 firewall should allow ping:
1. In Control Panel double click "Networking and Internet Connections"
2. Right click the connection which you would like to get pinged, and select "Properties"
3. On the Advanced-tab press the Settings-button
4. On the ICMP-tab tick "Allow incoming echo request"