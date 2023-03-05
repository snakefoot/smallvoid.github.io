---
title: 'Configure dialup modem to use maximum port speed'
date: '2001-10-01T23:25:56+02:00'
status: publish
permalink: /article/winxp-dialup-bps.html
author: Snakefoot
excerpt: 'Changing the maximum port speed to get a faster dialup connection.'
type: post
id: 422
category:
    - Network
tag:
    - dialup-modem
post_format: []
tags:
    - dialup-modem
---
Set BPS for the modem:

1. Open the **Control Panel**
2. Double click the **Phone and Modem options**-applet
3. Select the **Modems**-tab
4. Choose your modem and press the **Properties**-button
5. Select the **Modem**-tab
6. Set the **Maximum Port Speed** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
 
 Set BPS for the serial port:
1. Open the **Control Panel**
2. Double click the **Phone and Modem options**-applet
3. Select the **Modems**-tab
4. Choose your modem and press the **Properties**-button
5. Select the **Advanced**-tab
6. Press the **Change Default Preferences...**-button
7. Set the **Port Speed** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
8. Set the **Data Protocol** to **Forced EC** (If problems set back to **Standard**)
9. Set the **Compression** to **Enabled** (Unless using a WinModem)
10. Set the **Flow control** to **Hardware**
 
 Set BPS for the connection:
1. Open the **Control Panel**
2. Double click the **Network and Dial-up Connections**-applet
3. Right click your dial-up connection and choose **Properties**
4. Select the **General**-tab
5. Press the **Configure**-button.
6. Set the **Maximum Speed (bps)** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
 
 More Info [MS KB308022](http://support.microsoft.com/kb/308022 "Resources for troubleshooting modem problems in Windows XP [Q308022]")  
  
 Related [Optimize dialup modem connection](/article/winnt-dialup-connection.html)  
 Related [Configure maximum port speed for modem in Win2k](/article/win2k-dialup-bps.html)  