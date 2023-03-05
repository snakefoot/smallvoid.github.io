---
title: 'Configure dialup modem to use maximum port speed'
date: '2001-01-01T23:19:19+01:00'
status: publish
permalink: /article/win2k-dialup-bps.html
author: Snakefoot
excerpt: 'Changing the maximum port speed to get a faster dialup connection.'
type: post
id: 421
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
5. Select the **General**-tab (Here is also the modem-init-string)
6. Set the **Maximum Port Speed** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
 
 Set BPS for the serial port:
1. Open the **Control Panel**
2. Double click the **System**-applet
3. Select the **Hardware**-tab
4. Press the **Device Manager**-button
5. Expand the **Ports**-node
6. Double click the serial port, which your modem is attached to
7. Choose the **Port Settings**-tab
8. Set the **Bits Per Second** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
 
 Set BPS for the connection:
1. Open the **Control Panel**
2. Double click the **Network and Dial-up Connections**-applet
3. Right click your dial-up connection and choose **Properties**
4. Select the **General**-tab
5. Press the **Configure**-button.
6. Set the **Maximum Speed (bps)** to: 
  - 115200 if having a 56K modem
  - 57600 if having a 28.8K/33.6K modem
 
 Related [Optimize dialup modem connection](/article/winnt-dialup-connection.html)  
 Related [Configure maximum port speed for modem in WinXP](/article/winxp-dialup-bps.html)  