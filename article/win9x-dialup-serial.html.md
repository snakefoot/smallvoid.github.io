---
title: 'Optimize Dialup Modem and Serial port FIFO buffer in Windows 9x'
date: '2001-01-01T16:26:38+01:00'
status: publish
permalink: /article/win9x-dialup-serial.html
author: Snakefoot
excerpt: 'Configure the hardware settings for the dialup modem and serial port for optimal speed.'
type: post
id: 193
category:
    - Network
    - Network
    - Network
tag:
    - dialup-modem
    - serial-port
post_format: []
tags:
    - 'dialup-modem,serial-port'
---
To configure your modem:

1. Open **Control Panel**
2. Double click the **System**-applet
3. Select the **Device Manager**-fan
4. Expand the **Modems**-node and select properties for your modem
5. Select the **Connection**-fan and press the **Port Settings**-button, there enable FIFO and turn the sliders all the way up
6. Select the **Advanced**-fan and make sure that **Hardware flowcontrol**, **Error Correction** and **Compression** is enabled
7. Select the **Modem**-fan and change the BPS: 
  - 57600 if it is a 28.8/33.6K modem
  - 115200 if it is a 56K modem
 
 To configure the port the modem is attached to (If external modem):
1. Open **Control Panel**
2. Double click the **System**-applet
3. Select the **Device Manager**-fan
4. Select the **Ports**-node and select properties for the serial port the modem is attached to
5. Select the **Port Settings**-fan and change the **Bits Per Second**(BPS) to 115200 or higher, and make sure **Flowcontrol** is set to Hardware
6. On the **Port Settings**-fan press the **Advanced**-button and activate the FIFO buffer and turn the sliders all the way up.
 
 More info [MS KB131016](http://support.microsoft.com/kb/131016 "Settings for the 16550 UART FIFO Buffer [Q131016]")  