---
title: 'Disable/Uninstall Windows Messenger in Windows XP'
date: '2002-10-13T01:19:44+02:00'
status: publish
permalink: /article/windows-messenger-settings.html
author: Snakefoot
excerpt: 'Windows Messenger is an inter-message (IM) application created by Microsoft which is integrated into Microsoft Outlook.'
type: post
id: 470
category:
    - Troubleshoot
tag:
    - free-disk-space
    - windows-messenger
post_format: []
tags:
    - 'windows-messenger,free-disk-space'
---
[Windows Messenger](http://messenger.microsoft.com/) (Msnmsgr.exe) is an instant messaging client, which is included by default with Windows XP. It is a different product than [MSN Messenger](/article/msn-messenger-settings.html), as Windows Messenger includes tight integration with Microsoft Exchange, Microsoft Outlook, Microsoft Outlook Express, and the [Remote Assistance feature](/article/winnt-remote-assistance.html), but both clients can connect to the MSN network. Now the Windows Messenger and MSN Messenger applications have been replaced by a single product called [Windows Live Messenger](http://messenger.live.com/).  
  
 With Service Pack 1 it should be possible to remove Windows Messenger from Windows XP using Add/Remove programs in the Control Panel.  
  
 If this is not the case then there are different ways to handle it.  
- One can uninstall messenger by modifying the SYSOC.INF file, which will allow one to remove it through Add/Remove Programs in the Control Panel:
  > [See all Windows Components in Add/Remove for Win2k/WinXP](/article/winnt-add-remove-all.html)
- One can also uninstall messenger by running this command:
  > rundll32 advpack.dll,LaunchINFSection %windir%\\INF\\msmsgs.inf,BLC.Remove
- Windows Messenger can get into a conflict with MSN Messenger, where Windows Messenger tries to install it self every time using MSN Messenger. Repair this by running the following command and then Re-Install [Windows Messenger](http://www.microsoft.com/downloads/details.aspx?familyid=a8d9eb73-5f8c-4b9a-940f-9157a3b3d774).
  > msiexec /x {A433AE09-2126-4dad-9CBD-C1B05DC42787}
- One can stop messenger from starting with Outlook Express, by setting this DWORD registry value:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Outlook Express\]  
  >  Hide Messenger = 2
- One can avoid slow start of Outlook Express after disabling/uninstalling Messenger, by turning off Messenger Support in the Outlook Express menu:
  > Tools -&gt; Options -&gt; General Tab -&gt; Messenger Support
- One can avoid slow start of Outlook after disabling/uninstalling Messenger, by turning off Messenger Support in the Outlook menu:
  > Tools -&gt; Options -&gt; Other -&gt; Messenger Support
- One can avoid slow access to hotmail when having disabled/uninstalled messenger, by renaming this registry key:
  > \[HKEY\_CLASSES\_ROOT \\Messenger.MsgrObject\]  
  >   
  >  To :  
  >   
  >  \[HKEY\_CLASSES\_ROOT \\Messenger.MsgrObject-Old\]
- One can stop Messenger 4.5+ from starting, by setting these DWORD registry values:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Messenger \\Client\]  
  >  PreventRun = 1  
  >  PreventAutoRun = 1
- One can stop messenger from showing balloontip about creating a Passport account, by setting this BINARY registry value:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\MessengerService\]  
  >  PassportBalloon = 0A 00 00 00  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Internet Settings \\Passport\]  
  >  "RegistrationCompleted"=dword:00000001
- Disable the popup about messenger is still running when closing it with this BINARY registry value:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\MessengerService\]  
  >  DSBkgndMode = 01 00 00 00
 
 More Info [MS KB278887](http://support.microsoft.com/kb/278887 "MSN Messenger Service Cannot Perform File Transfers or Make Voice Connections Through NAT [Q278887]")  
 More Info [MS KB302089](http://support.microsoft.com/kb/302089 "How to Prevent Windows Messenger from Running on a Windows XP-Based Computer [Q302089]")  
 More Info [MS KB327390](http://support.microsoft.com/kb/327390 "Windows Messenger Starts When You Start Outlook Express After You Remove Access to Windows Messenger [Q327390]")  
 More Info [MS KB330117](http://support.microsoft.com/kb/330117 "Running both Windows Messenger and MSN Messenger 5.0 in Windows XP [Q330117]")  
  
 Credits [kellys-korner-xp.com](http://www.kellys-korner-xp.com/)