---
title: 'Optimizing the dialup handshake in Windows 9x'
date: '2001-01-01T16:36:48+01:00'
status: publish
permalink: /article/win9x-dialup-handshake.html
author: Snakefoot
excerpt: 'Make the dialup connection time faster by limiting the dialup protocols to only TCPIP.'
type: post
id: 194
category:
    - Network
    - Network
    - Network
tag:
    - dialup-modem
    - tcpip
post_format: []
tags:
    - 'dialup-modem,tcpip'
---
By standard when creating a modem connection in Win9x it is configured to log on to the ISP's network. This is not necessary and establishing the connection will be slow.  
  
 To disable this:

1. Double click **My Computer**-icon
2. Double click **Dial-Up Networking**-folder
3. Right click your ISP(Internet Service Provider) connection and choose properties
4. Select **Server Types**-fan
5. Uncheck **Log on to Network**
6. Uncheck **NetBEUI** and **IPX**, but leave **TCPIP** checked.
 
 More Info [MS KB130073](http://support.microsoft.com/kb/130073 "How to Decrease Logon Time to Internet Providers [Q130073]")  