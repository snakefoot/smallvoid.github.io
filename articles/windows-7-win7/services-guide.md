---
title: Windows 7 Services Guide
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/windows-7-win7/services-guide/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'How to tweak the services in Windows 7, with description of what services are unnecessary and can be disabled for security and performance.'
tags:
    - ''
---

##### Windows 7 Services Guide

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
| [ActiveX Installer (AxInstSV)](http://smallvoid.com/article/winnt-services-axinstsv.html) | Manual | Manual | Manual |
| [Adaptive Brightness](http://smallvoid.com/article/winnt-services-sensrsvc.html) | Manual | Manual | Manual |
| [Application Experience](http://smallvoid.com/article/winnt-services-aelookupsvc.html) | Manual | Manual (Care) | Manual |
| [Application Identity](http://smallvoid.com/article/winnt-services-appidsvc.html) | Manual | Manual | Manual |
| [Application Information](http://smallvoid.com/article/winnt-services-appinfo.html) | Manual | Manual | Manual |
| [Application Layer Gateway Service](http://smallvoid.com/article/winnt-services-alg.html) | Manual | Manual (Net) | Manual |
| [Application Management](http://smallvoid.com/article/winnt-services-appmgmt.html) | Manual | Manual | Manual |
| [Background Intelligent Transfer Service](http://smallvoid.com/article/winnt-services-bits.html) | Manual | Manual (Care) | Manual |
| [Base Filtering Engine](http://smallvoid.com/article/winnt-services-bfe.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [BitLocker Drive Encryption Service](http://smallvoid.com/article/winnt-services-bdesvc.html) | Manual | Manual | Manual |
| [Block Level Backup Engine Service](http://smallvoid.com/article/winnt-services-wbengine.html) | Manual | Manual | Manual |
| [Bluetooth Support Service](http://smallvoid.com/article/winnt-services-bthserv.html) | Manual | Manual | Manual |
| [BranchCache](http://smallvoid.com/article/winnt-services-peerdistsvc.html) | Manual | Manual | Manual |
| [Certificate Propagation](http://smallvoid.com/article/winnt-services-certpropsvc.html) | Manual | Manual | Manual |
| [CNG Key Isolation](http://smallvoid.com/article/winnt-services-keyiso.html) | Manual | Manual | Manual |
| [COM+ Event System](http://smallvoid.com/article/winnt-services-eventsystem.html) | Automatic | Automatic | Automatic |
| [COM+ System Application](http://smallvoid.com/article/winnt-services-comsysapp.html) | Manual | Manual | Manual |
| [Computer Browser](http://smallvoid.com/article/winnt-services-browser.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Credential Manager Service](http://smallvoid.com/article/winnt-services-vaultsvc.html) | Manual | Manual | Manual |
| [Cryptographic Services](http://smallvoid.com/article/winnt-services-cryptsvc.html) | Automatic | Automatic | Automatic |
| [DCOM Server Process Launcher](http://smallvoid.com/article/winnt-services-dcomlaunch.html) | Automatic | Automatic | Automatic |
| [Desktop Window Manager Session Manager](http://smallvoid.com/article/winnt-services-uxsms.html) | Automatic | Automatic | Disabled *(Trim) |
| [DHCP Client](http://smallvoid.com/article/winnt-services-dhcp.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Diagnostic Policy Service](http://smallvoid.com/article/winnt-services-dps.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Diagnostic Service Host](http://smallvoid.com/article/winnt-services-wdiservicehost.html) | Manual | Manual | Disabled *(Trim) |
| [Diagnostic System Host](http://smallvoid.com/article/winnt-services-wdisystemhost.html) | Manual | Manual | Disabled *(Trim) |
| [Disk Defragmenter](http://smallvoid.com/article/winnt-services-defragsvc.html) | Manual | Manual (Care) | Manual |
| [Distributed Link Tracking Client](http://smallvoid.com/article/winnt-services-trkwks.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Distributed Transaction Coordinator](http://smallvoid.com/article/winnt-services-msdtc.html) | Manual | Manual | Manual |
| [DNS Client](http://smallvoid.com/article/winnt-services-dnscache.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Encrypting File System (EFS)](http://smallvoid.com/article/winnt-services-efs.html) | Manual | Manual | Manual |
| [Extensible Authentication Protocol](http://smallvoid.com/article/winnt-services-eaphost.html) | Manual | Manual (Net) | Manual |
| [Fax](http://smallvoid.com/article/winnt-services-fax.html) | Manual | Manual | Manual |
| [Function Discovery Provider Host](http://smallvoid.com/article/winnt-services-fdphost.html) | Manual | Manual | Disabled *(Trim) |
| [Function Discovery Resource Publication](http://smallvoid.com/article/winnt-services-fdrespub.html) | Automatic | Automatic | Disabled *(Trim) |
| [Group Policy Client](http://smallvoid.com/article/winnt-services-gpsvc.html) | Automatic | Automatic | Automatic |
| [Health Key and Certificate Management](http://smallvoid.com/article/winnt-services-hkmsvc.html) | Manual | Manual (Net) | Manual |
| [HomeGroup Listener](http://smallvoid.com/article/winnt-services-homegrouplistener.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [HomeGroup Provider](http://smallvoid.com/article/winnt-services-homegroupprovider.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Human Interface Device Access](http://smallvoid.com/article/winnt-services-hidserv.html) | Manual | Manual | Manual |
| [IKE and AuthIP IPsec Keying Modules](http://smallvoid.com/article/winnt-services-ikeext.html) | Manual | Manual (Net) | Manual |
| [Interactive Services Detection](http://smallvoid.com/article/winnt-services-ui0detect.html) | Manual | Manual | Manual |
| [Internet Connection Sharing (ICS)](http://smallvoid.com/article/winnt-services-sharedaccess.html) | Disabled | Disabled | Disabled |
| [IP Helper](http://smallvoid.com/article/winnt-services-iphlpsvc.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [IPsec Policy Agent](http://smallvoid.com/article/winnt-services-policyagent.html) | Manual | Manual (Net) | Manual |
| [KtmRm for Distributed Transaction Coordinator](http://smallvoid.com/article/winnt-services-ktmrm.html) | Manual | Manual | Manual |
| [Link-Layer Topology Discovery Mapper](http://smallvoid.com/article/winnt-services-lltdsvc.html) | Manual | Manual (Net) | Manual |
| [Media Center Extender Service](http://smallvoid.com/article/winnt-services-mcx2svc.html) | Disabled | Disabled | Disabled |
| [Microsoft .NET Framework NGEN](http://smallvoid.com/article/winnt-services-clr-optimization.html) | Manual | Manual | Manual |
| [Microsoft iSCSI Initiator Service](http://smallvoid.com/article/winnt-services-msiscsi.html) | Manual | Manual | Manual |
| [Microsoft Software Shadow Copy Provider](http://smallvoid.com/article/winnt-services-swprv.html) | Manual | Manual | Manual |
| [Multimedia Class Scheduler](http://smallvoid.com/article/winnt-services-mmcss.html) | Automatic | Automatic (Audio) | Disabled *(Trim) |
| [Net.Tcp Port Sharing Service](http://smallvoid.com/article/winnt-services-nettcpportsharing.html) | Disabled | Disabled | Disabled |
| [Netlogon](http://smallvoid.com/article/winnt-services-netlogon.html) | Manual | Manual (Net) | Manual |
| [Network Access Protection Agent](http://smallvoid.com/article/winnt-services-napagent.html) | Manual | Manual (Net) | Manual |
| [Network Connections](http://smallvoid.com/article/winnt-services-netman.html) | Manual | Manual (Net) | Manual |
| [Network List Service](http://smallvoid.com/article/winnt-services-netprofm.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Network Location Awareness](http://smallvoid.com/article/winnt-services-nla.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Network Store Interface Service](http://smallvoid.com/article/winnt-services-nsi.html) | Automatic | Automatic (Net) | Automatic |
| [Offline Files](http://smallvoid.com/article/winnt-services-cscservice.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Parental Controls](http://smallvoid.com/article/winnt-services-wpcsvc.html) | Manual | Manual | Manual |
| [Peer Name Resolution Protocol](http://smallvoid.com/article/winnt-services-pnrpsvc.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Peer Networking Grouping](http://smallvoid.com/article/winnt-services-p2psvc.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Peer Networking Identity Manager](http://smallvoid.com/article/winnt-services-p2pimsvc.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Performance Logs & Alerts](http://smallvoid.com/article/winnt-services-pla.html) | Manual | Manual | Manual |
| [Plug and Play](http://smallvoid.com/article/winnt-services-plugplay.html) | Automatic | Automatic | Automatic |
| [PnP-X IP Bus Enumerator](http://smallvoid.com/article/winnt-services-ipbusenum.html) | Manual | Manual (Net) | Manual |
| [PNRP Machine Name Publication Service](http://smallvoid.com/article/winnt-services-pnrpautoreg.html) | Manual | Manual (Net) | Manual |
| [Portable Device Enumerator Service](http://smallvoid.com/article/winnt-services-wpdbusenum.html) | Manual | Manual | Disabled *(Trim) |
| [Power](http://smallvoid.com/article/winnt-services-power.html) | Automatic | Automatic (Audio) | Automatic |
| [Print Spooler](http://smallvoid.com/article/winnt-services-spooler.html) | Automatic | Automatic | Disabled *(Trim) |
| [Problem Reports and Solutions Control Panel Support](http://smallvoid.com/article/winnt-services-wercplsupport.html) | Manual | Manual | Manual |
| [Program Compatibility Assistant Service](http://smallvoid.com/article/winnt-services-pcasvc.html) | Automatic | Automatic (Care) | Automatic |
| [Protected Storage](http://smallvoid.com/article/winnt-services-protectedstorage.html) | Manual | Manual | Manual |
| [Quality Windows Audio Video Experience](http://smallvoid.com/article/winnt-services-qwave.html) | Manual | Manual | Manual |
| [Remote Access Auto Connection Manager](http://smallvoid.com/article/winnt-services-rasauto.html) | Manual | Manual (DUN) | Manual |
| [Remote Access Connection Manager](http://smallvoid.com/article/winnt-services-rasman.html) | Manual | Manual (DUN) | Manual |
| [Remote Desktop Configuration](http://smallvoid.com/article/winnt-services-sessionenv.html) | Manual | Manual | Manual |
| [Remote Desktop Services](http://smallvoid.com/article/winnt-services-remotedesktop.html) | Manual | Manual | Manual |
| [Remote Desktop Services UserMode Port Redirector](http://smallvoid.com/article/winnt-services-umrdpservice.html) | Manual | Manual | Manual |
| [Remote Procedure Call (RPC)](http://smallvoid.com/article/winnt-services-rpcss.html) | Automatic | Automatic | Automatic |
| [Remote Procedure Call (RPC) Locator](http://smallvoid.com/article/winnt-services-rpclocator.html) | Manual | Manual | Manual |
| [Remote Registry](http://smallvoid.com/article/winnt-services-remoteregistry.html) | Manual | Manual | Manual |
| [Routing and Remote Access](http://smallvoid.com/article/winnt-services-remoteaccess.html) | Disabled | Disabled | Disabled |
| [RPC Endpoint Mapper](http://smallvoid.com/article/winnt-services-rpceptmapper.html) | Automatic | Automatic | Automatic |
| [Secondary Logon](http://smallvoid.com/article/winnt-services-seclogon.html) | Manual | Manual | Manual |
| [Secure Socket Tunneling Protocol Service](http://smallvoid.com/article/winnt-services-sstpsvc.html) | Manual | Manual | Manual |
| [Security Accounts Manager](http://smallvoid.com/article/winnt-services-samss.html) | Automatic | Automatic | Automatic |
| [Security Center](http://smallvoid.com/article/winnt-services-wscsvc.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Server](http://smallvoid.com/article/winnt-services-lanmanserver.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [Shell Hardware Detection](http://smallvoid.com/article/winnt-services-shellhwdetection.html) | Automatic | Automatic | Disabled *(Trim) |
| [Smart Card](http://smallvoid.com/article/winnt-services-scardsvr.html) | Manual | Manual | Manual |
| [Smart Card Removal Policy](http://smallvoid.com/article/winnt-services-scpolicysvc.html) | Manual | Manual | Manual |
| [SNMP Trap](http://smallvoid.com/article/winnt-services-snmptrap.html) | Manual | Manual | Manual |
| [Software Protection](http://smallvoid.com/article/winnt-services-sppsvc.html) | Automatic | Automatic | Automatic |
| [SPP Notification Service](http://smallvoid.com/article/winnt-services-sppuinotify.html) | Manual | Manual | Manual |
| [SSDP Discovery](http://smallvoid.com/article/winnt-services-ssdpsrv.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [Storage Service](http://smallvoid.com/article/winnt-services-storsvc.html) | Manual | Manual | Manual |
| [Superfetch](http://smallvoid.com/article/winnt-services-sysmain.html) | Automatic | Automatic | Disabled *(Trim) |
| [System Event Notification Service](http://smallvoid.com/article/winnt-services-sens.html) | Automatic | Automatic | Automatic |
| [Tablet PC Input Service](http://smallvoid.com/article/winnt-services-tabletinputservice.html) | Manual | Manual | Manual |
| [Task Scheduler](http://smallvoid.com/article/winnt-services-schedule.html) | Automatic | Automatic (Care) | Automatic |
| [TCP/IP NetBIOS Helper](http://smallvoid.com/article/winnt-services-lmhosts.html) | Automatic | Disabled *(Trim) | Disabled *(Trim) |
| [Telephony](http://smallvoid.com/article/winnt-services-tapisrv.html) | Manual | Manual (DUN) | Disabled *(Trim) |
| [Themes](http://smallvoid.com/article/winnt-services-themes.html) | Automatic | Automatic | Disabled *(Trim) |
| [Thread Ordering Server](http://smallvoid.com/article/winnt-services-threadorder.html) | Manual | Manual | Manual |
| [TPM Base Services](http://smallvoid.com/article/winnt-services-tbs.html) | Manual | Manual | Manual |
| [UPnP Device Host](http://smallvoid.com/article/winnt-services-upnphost.html) | Manual | Manual (Net) | Disabled *(Trim) |
| [User Profile Service](http://smallvoid.com/article/winnt-services-profsvc.html) | Automatic | Automatic | Automatic |
| [Virtual Disk](http://smallvoid.com/article/winnt-services-vds.html) | Manual | Manual | Manual |
| [Volume Shadow Copy](http://smallvoid.com/article/winnt-services-vss.html) | Manual | Manual | Manual |
| [WebClient](http://smallvoid.com/article/winnt-services-webclient.html) | Manual | Manual | Manual |
| [Windows Audio](http://smallvoid.com/article/winnt-services-audiosrv.html) | Automatic | Automatic (Audio) | Automatic |
| [Windows Audio Endpoint Builder](http://smallvoid.com/article/winnt-services-audioendpointbuilder.html) | Automatic | Automatic (Audio) | Automatic |
| [Windows Backup](http://smallvoid.com/article/winnt-services-sdrsvc.html) | Manual | Manual | Manual |
| [Windows Biometric Service](http://smallvoid.com/article/winnt-services-wbiosrvc.html) | Manual | Manual | Manual |
| [Windows CardSpace](http://smallvoid.com/article/winnt-services-idsvc.html) | Manual | Manual | Manual |
| [Windows Color System](http://smallvoid.com/article/winnt-services-wcspluginservice.html) | Manual | Manual | Manual |
| [Windows Connect Now - Config Registrar](http://smallvoid.com/article/winnt-services-wcncsvc.html) | Manual | Manual (Net) | Manual |
| [Windows Defender](http://smallvoid.com/article/winnt-services-windefend.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Windows Driver Foundation - User-mode Driver Framework](http://smallvoid.com/article/winnt-services-wudfsvc.html) | Manual | Manual | Manual |
| [Windows Error Reporting Service](http://smallvoid.com/article/winnt-services-wersvc.html) | Manual | Manual | Manual |
| [Windows Event Collector](http://smallvoid.com/article/winnt-services-wecsvc.html) | Manual | Manual | Manual |
| [Windows Event Log](http://smallvoid.com/article/winnt-services-eventlog.html) | Automatic | Automatic | Automatic |
| [Windows Firewall](http://smallvoid.com/article/winnt-services-mpssvc.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [Windows Image Acquisition (WIA)](http://smallvoid.com/article/winnt-services-stisvc.html) | Manual | Manual | Disabled *(Trim) |
| [Windows Installer](http://smallvoid.com/article/winnt-services-msiserver.html) | Manual | Manual | Manual |
| [Windows Management Instrumentation](http://smallvoid.com/article/winnt-services-winmgmt.html) | Automatic | Automatic | Automatic |
| [Windows Media Center Receiver Service](http://smallvoid.com/article/winnt-services-ehrecvr.html) | Manual | Manual | Disabled *(Trim) |
| [Windows Media Center Scheduler Service](http://smallvoid.com/article/winnt-services-ehsched.html) | Manual | Manual | Disabled *(Trim) |
| [Windows Media Player Network Sharing Service](http://smallvoid.com/article/winnt-services-wmpnetworksvc.html) | Manual | Manual | Disabled *(Trim) |
| [Windows Modules Installer](http://smallvoid.com/article/winnt-services-trustedinstaller.html) | Manual | Manual | Manual |
| [Windows Presentation Foundation Font Cache](http://smallvoid.com/article/winnt-services-fontcache.html) | Manual | Manual | Manual |
| [Windows Remote Management (WS-Management)](http://smallvoid.com/article/winnt-services-winrm.html) | Manual | Disabled *(Lock) | Disabled *(Lock) |
| [Windows Search](http://smallvoid.com/article/winnt-services-wsearch.html) | Automatic | Automatic | Disabled *(Trim) |
| [Windows Time](http://smallvoid.com/article/winnt-services-w32time.html) | Manual | Manual (Care) | Manual |
| [Windows Update](http://smallvoid.com/article/winnt-services-wuauserv.html) | Automatic | Automatic (Care) | Disabled *(Trim) |
| [WinHTTP Web Proxy Auto-Discovery Service](http://smallvoid.com/article/winnt-services-winhttpautoproxysvc.html) | Manual | Manual | Disabled *(Trim) |
| [Wired AutoConfig](http://smallvoid.com/article/winnt-services-dot3svc.html) | Manual | Manual (Net) | Manual |
| [WLAN AutoConfig](http://smallvoid.com/article/winnt-services-wlansvc.html) | Manual | Manual (Net) | Manual |
| [WMI Performance Adapter](http://smallvoid.com/article/winnt-services-wmiapsrv.html) | Manual | Manual | Manual |
| [Workstation](http://smallvoid.com/article/winnt-services-lanmanworkstation.html) | Automatic | Automatic (Net) | Disabled *(Trim) |
| [WWAN AutoConfig](http://smallvoid.com/article/winnt-services-wwansvc.html) | Manual | Manual (Net) | Manual |

##### Other Service Guides:

-   [BlackViper.com: Windows 7 Service Configurations](http://www.blackviper.com/Windows_7/servicecfg.htm)
-   [TweakHound - Windows 7 Services Guide](http://www.tweakhound.com/windows7/tweaking/8.html)
-   [SpeedyVista.com: Windows 7 Services Guide](http://www.speedyvista.com/windows7/services.php)