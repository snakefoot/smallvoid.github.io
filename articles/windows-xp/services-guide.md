---
title: Windows XP Services Guide
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/windows-xp/services/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'How to tweak the services in Windows XP, with description of what services are unnecessary and can be disabled for security and performance.'
tags:
    - ''
---

##### Windows XP Services Guide

To access the service configuration:

-   Control Panel -> Administrative Tools -> [Services](http://smallvoid.com/article/winnt-services-config.html)-snapin.
-   Using the registry editor [Regedit to change service state](http://smallvoid.com/article/winnt-services-regedit.html).

A service has 3 basic startup states :

-   Disabled : The service will not be loaded (Some programs stops working, won't take memory, and quick boot time)
-   Manual : The service will be loaded on demand (Slow program start, will take memory when needed, and quick boot time)
-   Automatic : The service is loaded at boot time (Fast program start, will take memory, and slow boot time)

Explanation of recommendations:

-   **Recommended:** For users who prefers things safe and easy
-   **Trimmed:** For users who prefers only to have the most necessary started at the expense of manual maintenance and backup

Comments for recommendations (* = Recommendation divert from "default" state):

-   **Lock**: Increases security by disabling vulnerable features.
-   **Trim**: Lessens CPU/RAM usage on the expense of loosing special features.
-   **Care**: Enables Windows Self Maintenance, so it can take better care of it self.
-   **DUN** (Dial Up Networking): Enables Internet access through a dialup connection like Phone-, ISDN-, Cable- modem (internal or external).
-   **Net** (Network): Enables Internet access and filesharing via the network adapter to a hub, switch, router or another machine. The network is a simple one at home, without Domain Controller, Virtual Private Network or Internet Connection Sharing.

Select recommendation:

| Service | Default | Recommended | Trimmed |
| [Alerter](http://smallvoid.com/article/winnt-services-alerter.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Application Layer Gateway](http://smallvoid.com/article/winnt-services-alg.html) | Manual | Manual (Care) | Disabled *(Trim) |
| [Application Management](http://smallvoid.com/article/winnt-services-appmgmt.html) | Manual | Manual | Manual |
| [Automatic Updates](http://smallvoid.com/article/winnt-services-wuauserv.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Background Intelligent Transfer](http://smallvoid.com/article/winnt-services-bits.html) | Manual | Manual (Care) | Disabled *(Trim) |
| [Clipbook](http://smallvoid.com/article/winnt-services-clipsrv.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Computer Browser](http://smallvoid.com/article/winnt-services-browser.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [COM+ Event System](http://smallvoid.com/article/winnt-services-eventsystem.html) | Manual | Manual | Manual |
| [COM+ System Application](http://smallvoid.com/article/winnt-services-comsysapp.html) | Manual | Manual | Manual |
| [Cryptographic Services](http://smallvoid.com/article/winnt-services-cryptsvc.html) | Automatic | Automatic | Automatic |
| [DCOM Server Process Launcher](http://smallvoid.com/article/winnt-services-dcomlaunch.html) | Automatic | Automatic | Automatic |
| [DHCP Client](http://smallvoid.com/article/winnt-services-dhcp.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Distributed Link Tracking Client](http://smallvoid.com/article/winnt-services-trkwks.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Transaction Coordinator](http://smallvoid.com/article/winnt-services-msdtc.html) | Manual | Manual | Manual |
| [DNS Client](http://smallvoid.com/article/winnt-services-dnscache.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Error Reporting Service](http://smallvoid.com/article/winnt-services-ersvc.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Event Log](http://smallvoid.com/article/winnt-services-eventlog.html) | Automatic | Automatic | Automatic |
| [Extensible Authentication Protocol](http://smallvoid.com/article/winnt-services-eaphost.html) | Manual | Manual | Manual |
| [Fast User Switching Compatibility](http://smallvoid.com/article/winnt-services-fus.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [Fax Service](http://smallvoid.com/article/winnt-services-fax.html) | Manual | Manual | Manual |
| [Health Key and Certificate Management](http://smallvoid.com/article/winnt-services-hkmsvc.html) | Manual | Manual | Manual |
| [Help and Support](http://smallvoid.com/article/winnt-services-helpsvc.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [HTTP SSL](http://smallvoid.com/article/winnt-services-httpfilter.html) | Manual | Manual | Manual |
| [Human Interface Device Access](http://smallvoid.com/article/winnt-services-hidserv.html) | Manual | Manual | Disabled *(Trim) |
| [IMAPI CD-Burning COM Service](http://smallvoid.com/article/winnt-services-imapiservice.html) | Manual | Manual | Disabled *(Trim) |
| [Indexing Service](http://smallvoid.com/article/winnt-services-cisvc.html) | Manual | Disabled *(Trim) | Disabled *(Trim) |
| [IPSEC Services](http://smallvoid.com/article/winnt-services-policyagent.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Logical Disk Manager](http://smallvoid.com/article/winnt-services-dmserver.html) | Automatic | Automatic | Automatic |
| [Logical Disk Manager Administrative Service](http://smallvoid.com/article/winnt-services-dmadmin.html) | Manual | Manual | Manual |
| [Messenger](http://smallvoid.com/article/winnt-services-messenger.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [MS Software Shadow Copy Provider](http://smallvoid.com/article/winnt-services-swprv.html) | Manual | Manual | Manual |
| [NET Logon](http://smallvoid.com/article/winnt-services-netlogon.html) | Manual | Manual | Manual |
| [Netmeeting Remote Desktop Sharing](http://smallvoid.com/article/winnt-services-mnmsrvc.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network Access Protection Agent](http://smallvoid.com/article/winnt-services-napagent.html) | Manual | Manual | Manual |
| [Network Connections](http://smallvoid.com/article/winnt-services-netman.html) | Manual | Manual | Manual |
| [Network DDE](http://smallvoid.com/article/winnt-services-netdde.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network DDE DSDM](http://smallvoid.com/article/winnt-services-netddedsdm.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Network Location Awareness](http://smallvoid.com/article/winnt-services-nla.html) | Manual | Manual | Manual |
| [Network Provisioning Service](http://smallvoid.com/article/winnt-services-xmlprov.html) | Manual | Manual | Manual |
| [NT LM Security Support Provider](http://smallvoid.com/article/winnt-services-ntlmssp.html) | Manual | Manual | Manual |
| [Performance Logs and Alerts](http://smallvoid.com/article/winnt-services-sysmonlog.html) | Manual | Manual | Manual |
| [Plug and Play](http://smallvoid.com/article/winnt-services-plugplay.html) | Automatic | Automatic | Automatic |
| [Portable Media Serial Number Service](http://smallvoid.com/article/winnt-services-wmdmpmsp.html) | Manual | Manual | Manual |
| [Print Spooler](http://smallvoid.com/article/winnt-services-spooler.html) | Automatic | Automatic | Disabled *(Trim) |
| [Protected Storage](http://smallvoid.com/article/winnt-services-protectedstorage.html) | Automatic | Automatic | Automatic |
| [QoS RSVP](http://smallvoid.com/article/winnt-services-rsvp.html) | Manual | Manual | Manual |
| [Remote Access Auto Connection Manager](http://smallvoid.com/article/winnt-services-rasauto.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Access Connection Manager](http://smallvoid.com/article/winnt-services-rasman.html) | Manual | Manual (DUN) | Disabled * |
| [Remote Desktop Help Session Manager](http://smallvoid.com/article/winnt-services-rdsessmgr.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Remote Procedure Call (RPC)](http://smallvoid.com/article/winnt-services-rpcss.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC) Locator](http://smallvoid.com/article/winnt-services-rpclocator.html) | Manual | Manual | Manual |
| [Remote Registry Service](http://smallvoid.com/article/winnt-services-remoteregistry.html) | Automatic | Disabled *(Lock) | Disabled *(Lock) |
| [Removable Storage](http://smallvoid.com/article/winnt-services-ntmssvc.html) | Manual | Manual | Manual |
| [Routing and Remote Access](http://smallvoid.com/article/winnt-services-remoteaccess.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Secondary Logon](http://smallvoid.com/article/winnt-services-seclogon.html) | Automatic | Manual *(Trim) | Manual *(Trim) |
| [Security Accounts Manager](http://smallvoid.com/article/winnt-services-samss.html) | Automatic | Automatic | Automatic |
| [Security Center](http://smallvoid.com/article/winnt-services-wscsvc.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Server](http://smallvoid.com/article/winnt-services-lanmanserver.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Shell Hardware Detection](http://smallvoid.com/article/winnt-services-shellhwdetection.html) | Automatic | Automatic | Disabled *(Trim) |
| [Smart Card](http://smallvoid.com/article/winnt-services-scardsvr.html) | Manual | Manual | Manual |
| [Smart Card Helper](http://smallvoid.com/article/winnt-services-scarddrv.html) | Manual | Manual | Manual |
| [SSDP Discovery Service](http://smallvoid.com/article/winnt-services-ssdpsrv.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [System Event Notification](http://smallvoid.com/article/winnt-services-sens.html) | Automatic | Automatic | Automatic |
| [System Restore Service](http://smallvoid.com/article/winnt-services-srservice.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Task Scheduler](http://smallvoid.com/article/winnt-services-schedule.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [TCP/IP NetBIOS Helper Service](http://smallvoid.com/article/winnt-services-lmhosts.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Telephony](http://smallvoid.com/article/winnt-services-tapisrv.html) | Manual | Manual (DUN) | Disabled *(Trim) |
| [Telnet](http://smallvoid.com/article/winnt-services-telnet.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Terminal Services](http://smallvoid.com/article/winnt-services-termservice.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Themes](http://smallvoid.com/article/winnt-services-themes.html) | Automatic | Automatic | Disabled *(Trim) |
| [Uninterruptible Power Supply](http://smallvoid.com/article/winnt-services-ups.html) | Manual | Manual | Manual |
| [Upload Manager](http://smallvoid.com/article/winnt-services-uploadmgr.html) | Manual | Manual | Manual |
| [Universal Plug and Play Device Host](http://smallvoid.com/article/winnt-services-upnphost.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Volume Shadow Copy](http://smallvoid.com/article/winnt-services-vss.html) | Manual | Manual | Manual |
| [WebClient](http://smallvoid.com/article/winnt-services-webclient.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Windows Audio](http://smallvoid.com/article/winnt-services-audiosrv.html) | Automatic | Automatic | Automatic |
| [Windows Firewall/Internet Connection Sharing (ICS)](http://smallvoid.com/article/winxp-services-sharedaccess.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Windows Image Acquisition (WIA)](http://smallvoid.com/article/winnt-services-stisvc.html) | Manual | Manual | Disabled *(Trim) |
| [Windows Installer](http://smallvoid.com/article/winnt-services-msiserver.html) | Manual | Manual | Manual |
| [Windows Management Instrumentation](http://smallvoid.com/article/winnt-services-winmgmt.html) | Automatic | Automatic | Automatic |
| [Windows Management Instrumentation Driver Extentions](http://smallvoid.com/article/winnt-services-wmi.html) | Manual | Manual | Manual |
| [Windows Time](http://smallvoid.com/article/winnt-services-w32time.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Wired AutoConfig](http://smallvoid.com/article/winnt-services-dot3svc.html) | Manual | Manual | Manual |
| [Wireless Zero Configuration](http://smallvoid.com/article/winnt-services-wzcsvc.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [WMI Performance Adapter](http://smallvoid.com/article/winnt-services-wmiapsrv.html) | Manual | Manual | Manual |
| [Workstation](http://smallvoid.com/article/winnt-services-lanmanworkstation.html) | Automatic | Automatic (Net) | Disabled *(Trim) |

##### Other Service Guides:

-   [Microsoft : Windows XP Default settings for services](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/sys_srv_default_settings.mspx)
-   [3DSpotlight : Windows XP Services tweak guide](http://www.3dspotlight.com/tweaks/winxp_services/index.shtml)
-   [Black Viper's Windows XP Services Configurations](http://www.blackviper.com/WinXP/servicecfg.htm) - [Mirror](http://web.archive.org/web/20050401024021/http://www.blackviper.com/WinXP/servicecfg.htm) - [Debunked](http://forums.anandtech.com/messageview.aspx?catid=34&threadid=1678445&arctab=y "Performance-oriented Windows tweaking")
-   [ElderGeek : Services Guide for Windows XP](http://www.theeldergeek.com/services_guide.htm)
-   [Gene Goldring : Removal Recommendations For Windows XP Services](http://www.beemerworld.com/tips/servicesxp.htm)
-   [XpMania : The BIG XP Services Explanation](http://www.pro-networks.org/XPMaNiA/services.shtml "www.xpmania.windowspro.net")
-   [TweakHound.com : Super XP Tweaking Guide for Services](http://www.tweakhound.com/xp/xptweaks/supertweaks6.htm "TweakHound's Super XP Tweaking Guide Page")
-   [PCStats.com : Beginners Guides: Understanding and Tweaking WindowsXP Services](http://www.pcstats.com/articleview.cfm?articleID=1759)
-   [CastleCops.com - List of Windows XP/NT services (Also non-Microsoft)](http://castlecops.com/o23-all.html)