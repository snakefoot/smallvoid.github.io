---
title: Messenger
date: '2000-06-06T14:11:08+02:00'
status: publish
permalink: /article/winnt-services-messenger.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Messenger service.'
type: post
id: 561
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Is used to send/show messages and alerts on the local machine or to remote machines.  
  
 It has lately been used by spammers to send popup messages with advertising to internet users who doesn't have this service disabled or haven't enabled a firewall.  
  
 Note this service should not be confused with [Windows Live Messenger](http://messenger.live.com/) (Replaces [Windows Messenger](http://messenger.microsoft.com/) and [MSN Messenger](http://messenger.msn.com/)). Disabling this service will not affect the operation of these Instant Messaging (IM) applications.  
  
 Note the service might not start in the following situations: - If the network bindings between protocols and network adapter are screwed. Uninstall and reinstall the protocols and check the bindings.
- If the service detects another computer with the same name, can be caused by not being registered properly in the WINS, DNS server
- If there is a mismatch between binaries, can be fixed by reinstalling the service pack
 
 More Info [MS KB101355](http://support.microsoft.com/kb/101355 "Service Control Manager Event 7024 (2270) [Q101355]")  
 More Info [MS KB137143](http://support.microsoft.com/kb/137143 "WinPopup Utility Not Supported In Windows NT [Q137143]")  
 More Info [MS KB168893](http://support.microsoft.com/kb/168893 "Messenger Service of Windows [Q168893]")  
 More Info [MS KB330117](http://support.microsoft.com/kb/330117 "Running Both Windows Messenger and MSN Messenger 5.0 in Windows XP [Q330117]")  
 More Info [MS KB330904](http://support.microsoft.com/kb/330904 "Messenger Service Window That Contains an Internet Advertisement Appears [Q330904]")  
  
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