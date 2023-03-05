---
title: 'Configure whether to display balloon tips'
date: '2002-10-12T20:05:02+02:00'
status: publish
permalink: /article/winnt-balloon-tip.html
author: Snakefoot
excerpt: 'Configure what balloon tips Windows should display above the system tray.'
type: post
id: 403
category:
    - Desktop
    - Desktop
tag:
    - balloon-tip
post_format: []
tags:
    - balloon-tip
---
Windows XP started using balloon tips heavily, as an attempt to help the average user to understand what is happening on the computer. The balloon tip is shown like a tooltip bubble just above the taskbar to the right near the system tray (also known as the notification area). For the more experienced user the balloon tips can become a pain, but it is possible to configure their behavior.  
  
 To disable balloon tips in the notification area completely:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  EnableBalloonTips = 0  
>   
>  More Info [MS KB279771](http://support.microsoft.com/kb/279771 "Description of Notification Area Settings [Q279771]")  
>  More Info [MS KB307729](http://support.microsoft.com/kb/307729 "HOW TO: Disable Notification Area Balloon Tips in Windows XP [Q307729]")

 To disable "Show popup description for folder and desktop items" (Folder Options):
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  ShowInfoTip = 0

 To disable tooltip for folders:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  FolderContentsInfoTip = 0

 To disable tooltips for the start button:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  StartButtonBalloonTip = 0

 To disable the balloon tip "To see the hidden icons, click this button":
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\TrayNotify\]  
>  BalloonTip = 1

 To disable tooltips for the start menu:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoSMBalloonTip = 1

 To disable the welcome screen presented after login:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoWelcomeScreen = 1

 To disable the New Hardware Found balloon tooltips:
> \[HKEY\_LOCAL\_MACHINE \\Software \\Policies \\Microsoft \\Windows \\DeviceInstall \\Settings\]  
>  DisableBalloonTips = 1

 To disable the Highlighting of newly installed applications:
1. Press the **Start-button** and right-click at the top of the **Start-Menu** where your name is displayed and select **Properties**
2. This will open the **Taskbar and Start Menu Properties**-dialog
3. Select the **Start-Menu**-tab and press **Customize**
4. Select the **Advanced**-tab and clear the **Highlight newly installed programs**-checkbox
5. The above steps should be reflected in this registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
  >  Start\_NotifyNewApps = 0
 
 To disable the tour balloon tips:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Applets \\Tour\]  
>  RunCount = 0 (Default = 3)  
>   
>  More Info [MS KB311489](http://support.microsoft.com/kb/311489 "How to Suppress the Windows Tour Prompt in Windows XP [Q311489]")

 To disable the [printer spooler](/article/winnt-services-spooler.html) notification balloon tips:
> \[HKEY\_CURRENT\_USER \\Printers \\Settings\]  
>  EnableBalloonNotificationsLocal = 0  
>  EnableBalloonNotificationsRemote = 0  
>   
>  More Info [MS KB831582](http://support.microsoft.com/kb/831582 "No network printer notifications appear even though the "Show informational notifications for network printers" check box is selected in Windows XP [Q831582]")

 <a name="SECURITY_CENTER"></a> To disable the [Security Center](/article/winnt-services-wscsvc.html) notification balloon tips:
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Security Center\]  
>  FirewallDisableNotify = 1 (0 = Firewall notifications)  
>  UpdatesDisableNotify = 1 (0 = Automatic updates notifications)  
>  AntiVirusDisableNotify = 1 (0 = Antivirus notifications)  
>  UACDisableNotify = 1 (0 = [Vista UAP](/article/winnt-user-account-protection.html) notifications)

 To disable the "This device could perform faster if it was plugged in to a high speed port":
1. Open the Device Manager and expand "USB Controller"
2. Right-click the USB Controller(s) and select Properties
3. Select the Advanced-tab and tick "Don't show USB errors (or similar)"
 
 To disable Plug and Play messages like "Found New Hardware":
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\PlugPlay \\Parameters\]  
>  SuppressUI = 1 (Windows 2003/XP64 only)  
>  SuppressNewHWUI = (Windows XP)  
>   
>  More Info [MS KB311489](http://support.microsoft.com/kb/938596 "Hotfix adds new functionality to suppress Plug and Play-related UI messages in Windows Server 2003 or in Windows XP") (Requires XP SP3 to recognize registry keys)

 To disable the "There are unused icons on your desktop":
1. Open the Control Panel and go to Display Properties
2. Select the Desktop-tab and press the "Customize Desktop"-button
3. Untick "Run Desktop Cleanup Wizard every 60 days"