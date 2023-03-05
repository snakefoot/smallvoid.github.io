---
title: 'Changing the available bit rates for encoding mp3'
date: '2001-11-29T01:55:05+01:00'
status: publish
permalink: /article/media-player-mp3-encoding.html
author: Snakefoot
excerpt: 'Configure the bit rate of the predefined quality levels for mp3 encoding in Media Player 8.'
type: post
id: 280
category:
    - Tips
tag:
    - media-player
    - mp3
post_format: []
tags:
    - 'media-player,mp3'
---
Media Player 8 has predefined levels for the encoding quality of mp3 files.  
  
 Change/Add these DWORD decimal values to configure these levels:

> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\MediaPlayer \\Settings \\MP3Encoding\]  
>  LowRate=56000  
>  MediumRate=64000  
>  MediumHighRate=128000  
>  HighRate=192000

 Credits [www.mdgx.com](http://www.mdgx.com/)