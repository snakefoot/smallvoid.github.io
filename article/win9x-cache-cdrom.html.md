---
title: 'Configure the read-ahead cache for cdrom/dvd drives'
date: '2001-02-10T23:51:40+01:00'
status: publish
permalink: /article/win9x-cache-cdrom.html
author: Snakefoot
excerpt: 'How to increase the size of the read ahead cache used for cdrom and dvd drives.'
type: post
id: 101
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - cdrom-drive
    - disk-performance
    - dvd-drive
    - file-cache
post_format: []
tags:
    - 'file-cache,cdrom-drive,dvd-drive,disk-performance'
---
If you feel that you need more cache than what is recommended for a 4x CDROM then you should try this.  
  
 This is done in the registry with the following values :

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\FileSystem \\CDFS\]  
>  CacheSize = 619 (The Default)  
>  Prefetch = 228 (The Default for for 4x)

- **CacheSize** - The amount of 2 KByte pages used for caching
- **Prefetch** - The read ahead buffer which is depending on drive speed
 
 It is possible that the values can be saved in both DWORD and BINARY, you keep the value-type which you have already when setting these values:  
<table border="1"><tr><th>CacheSize </th><th>Memory </th><th>Decimal</th><th>Binary </th><th>DWORD </th></tr><tr><td>Default </td><td>1238 KB</td><td>619 </td><td>6b,02,00,00 </td><td>0000026b </td></tr><tr><td>Medium </td><td>2476 KB</td><td>1238 </td><td>d6,04,00,00 </td><td>000004d6 </td></tr><tr><td>Large </td><td>4952 KB</td><td>2476 </td><td>ac,09.00,00 </td><td>000009ac </td></tr></table>

<table border="1"><tr><th>Prefetch </th><th>Decimal </th><th>Binary </th><th>DWORD </th></tr><tr><td>4x (Default) </td><td>228 </td><td>e4,00,00,00 </td><td>000000e4 </td></tr><tr><td>8x </td><td>448 </td><td>c0,01,00,00 </td><td>000001c0 </td></tr><tr><td>16x </td><td>896 </td><td>80,03,00,00 </td><td>00000380 </td></tr><tr><td>32X </td><td>1792 </td><td>00,07,00,00 </td><td>00000700 </td></tr></table>