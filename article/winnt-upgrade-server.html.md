---
title: 'Convert from Windows Workstation to Server Edition'
date: '2002-03-21T23:45:58+01:00'
status: publish
permalink: /article/winnt-upgrade-server.html
author: Snakefoot
excerpt: 'Utilities that can change the configuration of a Windows installation so it becomes a server edition.'
type: post
id: 451
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - crippled
post_format: []
tags:
    - crippled
---
[O'reilley](http://www.oreilly.com/news/differences_nt.html "Differences Between NT Server and Workstation Are Minimal") has described that Mark Russinovich created an utility called NTTune, which could change a Windows NT4 Workstation into a Windows NT4 Server edition. This was possible because there is almost no difference between the two editions. NTTune was never released to the public, but the details of the changes was.  
  
 Later others have followed the foot steps of Mark Russinovich and have created their own utilities that makes the same changes as NTTune: - [NTSwitch](http://smallvoid.orgfree.com/?file=ntswitch.zip) by [3am](http://www.03am.com/).
- [TweakNT](http://smallvoid.orgfree.com/?file=tweaknt.zip)
  - Do not convert to Tablet PC (TabPC) or Media Center (MCE) if running corporate edition of XP (If having done so anyway, then it can be reverted by booting into safemode and running TweakNT again).
 
 Note some have claimed that the changes made by these utilities removed the [max limit of only 10 inbound concurrent sessions](/article/winnt-network-connection-limit.html). If converting from a Professional / Workstation to a Server edition, then one will experience that the server edition will automatically allocate more memory to take the role as network server.  
  
 Note in the rare situation where one wants to use a server edition of Windows as a desktop operating system, then these utilities can be used to downgrade the Windows edition. This can be useful when using utilities that will only install on the Professional or Workstation edition of Windows.  
  
 More Info [NT 4.0 Worksation =&lt; NT 4.0 Server](http://www.lehigh.edu/~rjm2/ntwntw.html) ([Mirror](http://web.archive.org/web/*/http://www.lehigh.edu/~rjm2/ntwntw.html))