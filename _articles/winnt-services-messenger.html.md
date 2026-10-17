---
title: Messenger
date: '2000-06-06T14:11:08+02:00'
permalink: /article/winnt-services-messenger.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Messenger service.'
type: post
id: 561
categories:
    - windows-2000_services
    - windows-nt4_services
    - windows-2003_services
    - windows-xp_services
tags: []
---
##### Description:

 Is used to send/show messages and alerts on the local machine or to remote machines.  
  
 It has lately been used by spammers to send popup messages with advertising to internet users who doesn't have this service disabled or haven't enabled a firewall.  
  
 Note this service should not be confused with [Windows Live Messenger](http://messenger.live.com/) (Replaces [Windows Messenger](http://messenger.microsoft.com/) and [MSN Messenger](http://messenger.msn.com/)). Disabling this service will not affect the operation of these Instant Messaging (IM) applications.  
  
 Note the service might not start in the following situations:
- If the network bindings between protocols and network adapter are screwed. Uninstall and reinstall the protocols and check the bindings.
- If the service detects another computer with the same name, can be caused by not being registered properly in the WINS, DNS server
- If there is a mismatch between binaries, can be fixed by reinstalling the service pack
 
 More Info <a href="https://www.bing.com/search?q=KB+101355+Q101355" rel="nofollow" title="Service Control Manager Event 7024 (2270) [Q101355]">MS KB101355</a>  
 More Info <a href="https://www.bing.com/search?q=KB+137143+Q137143" rel="nofollow" title="WinPopup Utility Not Supported In Windows NT [Q137143]">MS KB137143</a>  
 More Info <a href="https://www.bing.com/search?q=KB+168893+Q168893" rel="nofollow" title="Messenger Service of Windows [Q168893]">MS KB168893</a>  
 More Info <a href="https://www.bing.com/search?q=KB+330117+Q330117" rel="nofollow" title="Running Both Windows Messenger and MSN Messenger 5.0 in Windows XP [Q330117]">MS KB330117</a>  
 More Info <a href="https://www.bing.com/search?q=KB+330904+Q330904" rel="nofollow" title="Messenger Service Window That Contains an Internet Advertisement Appears [Q330904]">MS KB330904</a>  
  
##### Recommended State:

- Disabled, for security measures.
- Automatic, if fallen in love with the NET SEND command.

##### Default State:

- WinNT4/2k/Xp: Automatic.
- WinXP SP2: Disabled.
- Win2k3: Disabled.

##### Process Name:

- Win2k: [services.exe](/article/winnt-services-wrapper.html) (Messenger)
- WinXP/Win2k3: [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Messenger)

##### Supports:

- None

##### Depends:

- [Plug and Play](/article/winnt-services-plugplay.html) (WinXP/Win2k3 only)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Workstation](/article/winnt-services-lanmanworkstation.html)