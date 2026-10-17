---
title: 'Turn off Himem.sys memory testing'
date: '2000-01-01T15:47:24+01:00'
permalink: /article/himem-sys-memory-test.html
author: Snakefoot
excerpt: 'How to configure Himem.sys so it will not perform memory testing.'
type: post
id: 45
categories:
    - ms-dos_tips
tags:
    - himem-sys
    - memory-testing
---
Edit CONFIG.SYS and insert/update this line to disable the memory testing:

> DEVICE=C:\\DOS\\HIMEM.SYS /TESTMEM:OFF

 Note the memory testing can be useful if testing RAM timings in the motherboard BIOS, as it can verify that the RAM operates properly.  
  
 More Info <a href="https://www.bing.com/search?q=KB+109845+Q109845" rel="nofollow" title="Troubleshooting HIMEM.SYS 3.10 XMS Test (TESTMEM) Failures [Q109845]">MS KB109845</a>