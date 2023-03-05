---
title: 'Configure MSN Messenger'
date: '2005-09-25T01:28:20+02:00'
status: publish
permalink: /article/msn-messenger-settings.html
author: Snakefoot
excerpt: 'MSN Messenger is an application by Microsoft that allows one to chat with friends and family.'
type: post
id: 469
category:
    - Troubleshoot
    - Troubleshoot
tag:
    - msn-messenger
post_format: []
tags:
    - msn-messenger
---
[MSN Messenger](http://messenger.msn.com/) was originally a different product than [Windows Messenger](/article/windows-messenger-settings.html), but now they have been replaced by a single product called [Windows Live Messenger](http://messenger.live.com/).
- Removing the tabs from MSN Messenger 7.x (DWORD):
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\MSNMessenger\]  
  >  DisableTabs = 1
- Disabling MSN today at startup (BINARY):
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\MSNMessenger\]  
  >  DisableMSNToday = 01 00 00 00
- Disable popup about messenger is still running when closing (BINARY):
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\MSNMessenger\]  
  >  DSBkgndMode = 01 00 00 00
 
 Credits [sanx.org](http://www.sanx.org/)