---
title: 'Turn off Himem.sys memory testing'
date: '2000-01-01T15:47:24+01:00'
status: publish
permalink: /article/himem-sys-memory-test.html
author: Snakefoot
excerpt: 'How to configure Himem.sys so it will not perform memory testing.'
type: post
id: 45
category:
    - Tips
tag:
    - himem-sys
    - memory-testing
post_format: []
tags:
    - 'himem-sys,memory-testing'
---
Edit CONFIG.SYS and insert/update this line to disable the memory testing:

> DEVICE=C:\\DOS\\HIMEM.SYS /TESTMEM:OFF

 Note the memory testing can be useful if testing RAM timings in the motherboard BIOS, as it can verify that the RAM operates properly.  
  
 More Info [MS KB109845](http://support.microsoft.com/kb/109845 "Troubleshooting HIMEM.SYS 3.10 XMS Test (TESTMEM) Failures [Q109845]")