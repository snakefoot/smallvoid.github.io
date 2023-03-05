---
title: 'Configure the popup blocker in Internet Explorer'
date: '2005-09-25T00:53:14+02:00'
status: publish
permalink: /article/ie-popup-blocker.html
author: Snakefoot
excerpt: 'Windows XP SP2 extends the Internet Explorer with a popup blocking feature.'
type: post
id: 322
category:
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
    - 'Internet Explorer (IE8)'
tag:
    - popup-blocking
    - popups
post_format: []
tags:
    - 'popup-blocking,popups'
---
Internet Explorer was extended with a popup-blocker since IE6 SP2 (Included with WinXP SP2). When a popup is blocked, then it will display a popup information bar, where the user can control whether the popup should remain blocked. It blocks pop-up windows that appear outside the browser itself (To avoid covering the status bar, address bar, or a security dialog), and makes it harder for pop-ups to masquerade as system dialogs. It is possible to control how this popup-blocker should operate by clicking on Tools -&gt; Popup Blocker -&gt; Popup Blocker Settings...

- Whether the popup-blocker is enabled (This is the checkbox on the privacy tab in the Internet Control Panel):
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  PopupMgr = "yes" ("no" = Disabled, "yes" = Enabled, Default = "yes")
- Show the IE Information Band when a popup is blocked:
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  UseSecBand = 1 (0 = Disabled, 1 = Enabled; Default = 1)
- Play sound when a popup is blocked:
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  PlaySound = 1 (0 = Disabled, 1 = Enabled; Default = 1)
- Block popups caused by user actions (Ex. clicking a link):
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  BlockUserInit = 0 (0 = Disabled, 1 = Enabled; High = 1, Medium = 0, Low = 0)
- Block delayed popups caused by user actions:
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  UseTimerMethod = 1 (0 = Disabled, 1 = Enabled; High = 0, Medium = 0, Low = 1)  
  >  UserInitTimeout = ?
- Hook messages going to ActiveX controls, if disabled then a control may not open a new window:
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  UseHooks = 1 (0 = Disabled, 1 = Enabled; High = 0, Medium = 1, Low = 1)
- Block popups presented on web-sites accessed with HTTPS:
  > \[HKEY\_CURRENT\_USER \\ Software \\Microsoft \\Internet Explorer \\New Windows\]  
  >  AllowHTTPS = 1 (0 = Disabled, 1 = Enabled; High = 0, Medium = 0, Low = 1)
 
 More info [Microsoft Technet: Tales from the Script](http://www.microsoft.com/technet/community/columns/scripts/default.mspx)  