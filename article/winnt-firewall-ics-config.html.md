---
title: 'Configure and troubleshoot Windows Firewall and ICS'
date: '2007-06-08T00:04:45+02:00'
status: publish
permalink: /article/winnt-firewall-ics-config.html
author: Snakefoot
excerpt: 'How to get a non-working Windows Firewall service started with a configuration reset.'
type: post
id: 630
category:
    - Troubleshoot
tag:
    - firewall
post_format: []
tags:
    - firewall
---
When trying to configure the [Windows Firewall](/article/winnt-services-sharedaccess.html) using firewall.cpl in Windows XP, then it will give the following error if the service is not running:

> Windows Firewall settings cannot be displayed because the associated service is not running. Do you want to start the Windows Firewall/Internet Connection Sharing (ICS) service?  
>   
>  Due to an unidentified problem, Windows cannot display Windows Firewall settings.

 When trying to start the Windows Firewall service, then it might give one of the following errors:
 > Windows cannot start the Windows Firewall/Internet Connection Sharing (ICS) service.  
>   
>  An error occurred while Internet Connection Sharing was being enabled. The dependency service or group failed to start.

 The cause of these problems can either be that one is using [Windows Live OneCare](http://safety.live.com/) (Disables the Windows firewall service), or that the Windows Firewall service has a faulty configuration or the components it depends on are corrupt.  
  
 Check that the following services are running properly, which the Windows Firewall depends upon:
- [Application Layer Gateway Service](/article/winnt-services-alg.html)
- [Network Connections](/article/winnt-services-netman.html)
- [Network Location Awareness (NLA)](/article/winnt-services-nla.html)
- [Plug and Play](/article/winnt-services-plugplay.html)
- [Remote Access Auto Connection Manager](/article/winnt-services-rasauto.html)
- [Remote Access Connection Manager](/article/winnt-services-rasman.html)
- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)
- [Telephony](/article/winnt-services-tapisrv.html)
- More Info [MS KB827328](http://support.microsoft.com/kb/827328 ""Error 1068" Error Message When You Try to Turn On Internet Connection Sharing [Q827328]")
 
 To repair the configuration of the Windows Firewall open a command prompt and run this command:
 > NETSH FIREWALL RESET

 If the Windows Firewall service still fails to start, then try to reinstall the Windows Firewall with this command (Followed by the command above to reset the configuration):
 > Rundll32 setupapi,InstallHinfSection Ndi-Steelhead 132 %windir%\\inf\\netrass.inf  
 >   
 >  More Info [MS KB920074](http://support.microsoft.com/kb/920074 "You cannot start the Windows Firewall service in Windows XP SP2 [Q920074]")

 If the Windows Firewall service still fails to start, then try to [repair the TCP/IP and Winsock interface](/article/winnt-netsh.html) with these commands:
 > netsh int ip reset  
 >  netsh winsock reset

 If the Windows Firewall service still fails to start, then try to [repair the WMI Repository](/article/winnt-wmi-config.html) with this command:
 > rundll32 wbemupgd, UpgradeRepository

 More Info [MS KB892199](http://support.microsoft.com/kb/892199 "You cannot start the Windows Firewall service in Windows XP Service Pack 2 [Q892199]")  
  
 Credits [WindowsXP.mvps.org](http://windowsxp.mvps.org/sharedaccess.htm)