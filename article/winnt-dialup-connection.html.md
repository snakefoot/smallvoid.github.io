---
title: 'Optimize dialup modem connection'
date: '2001-01-01T23:29:10+01:00'
status: publish
permalink: /article/winnt-dialup-connection.html
author: Snakefoot
excerpt: 'Make dialup modem faster at etablishing a connection and with better connection speed.'
type: post
id: 423
category:
    - Network
    - Network
tag:
    - dialup-modem
    - flow-control
    - modem-compression
    - tcpip
    - winmodem
post_format: []
tags:
    - 'dialup-modem,tcpip,flow-control,modem-compression,winmodem'
---
Only use TCP/IP for the Internet connection (For performance and security):

1. Open the **Control Panel**
2. Double click the **Network and Dial-up Connections**-applet
3. Right click your dial-up connection and choose **Properties**
4. Select the **Networking**-tab
5. Uninstall or untick all Components except **Internet Protocol (TCPIP)**
6. Select the **Internet Protocol (TCPIP)** and choose **Properties**
7. Press the **Advanced**-button
8. On the **General**-tab tick **Use IP header compression** (Can increase ping time, but will improve download)
9. On the **WINS**-tab tick **Disable NetBIOS over TCP/IP**
 
 Optimize the connection to the dial-up server:
1. Open the **Control Panel**
2. Double click the **Network and Dial-up Connections**-applet
3. Right click your dial-up connection and choose **Properties**
4. Select the **Networking**-tab
5. In the dial-up server drop-down box select **PPP:Windows 95/98/NT4/2000, Internet**
6. Press the **Settings**-button and configure the **PPP Settings**: 
  - Check **Enable LCP extensions** (Unless having problems with connecting to ISP, More Info [RFC 1570](http://www.faqs.org/rfcs/rfc1570.html "PPP LCP (Link Control Protocol) Extensions"))
  - Uncheck **Enable software compression** (Unless using a Winmodem)
  - Uncheck **Negotiate multi-link for single link connections** (Unless using multiple modems, More Info [MS KB307849](http://support.microsoft.com/kb/307849 "HOW TO: Set Up Multiple-Device (Multilink) Dialing in Windows XP [Q307849]"))
 
 Optimize the hardware features for the connection:
1. Open the **Control Panel**
2. Double click the **Network and Dial-up Connections**-applet
3. Right click your dial-up connection and choose **Properties**
4. Select the **General**-tab
5. Press the **Configure**-button. 
  - Check **Enable hardware flow control**
  - Check **Enable modem error control**
  - Check **Enable modem compression** (Unless using a Winmodem)
 
 More info [MS KB244603](http://support.microsoft.com/kb/244603 "Error Message: TCP/IP CP Reported Error 733 [Q244603]")  
 More info [MS KB307849](http://support.microsoft.com/kb/307849 "HOW TO: Set Up Multiple-Device (Multilink) Dialing in Windows XP [Q307849]")  
 More info [MS KB314455](http://support.microsoft.com/kb/314455 ""Error 691" Error Message When You Try to Connect to Your ISP [Q314455]")  
  
 Related [Configure maximum port speed for modem in Win2k](/article/win2k-dialup-bps.html)  
 Related [Configure maximum port speed for modem in WinXP](/article/winxp-dialup-bps.html)  