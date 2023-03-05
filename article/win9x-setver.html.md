---
title: 'Stop Setver.exe from loading automatically into memory'
date: '2000-01-01T19:19:18+01:00'
status: publish
permalink: /article/win9x-setver.html
author: Snakefoot
excerpt: 'How to block Setver.exe from loading to save conventional memory.'
type: post
id: 91
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - conventional-memory
    - setver
post_format: []
tags:
    - 'setver,conventional-memory'
---
Windows 9x loads Himem.sys and Ifshlp.sys automatically eventhough they are not specified in the Config.sys. But it also loads SETVER.EXE, which is actually never needed and takes up conventional memory.  
  
 SETVER.EXE resides in the WINDOWS directory and if moved to the WINDOWS\\COMMAND directory it will keep it from being loaded automatically at boot.