---
title: 'Configure the login and Welcome Screen in Win7'
date: '2009-11-29T23:48:09+01:00'
status: publish
permalink: /article/win7-logon-screen.html
author: Snakefoot
excerpt: 'Microsoft Windows 7 no longer have the classic logon screen, which has been replaced by the Welcome Screen.'
type: post
id: 822
category:
    - Tips
tag:
    - branding
    - login-screen
    - welcome-screen
    - windows-login
post_format: []
tags:
    - 'windows-login,welcome-screen,login-screen,branding'
---
Windows 7 no longer supports the classic logon screen, that is available in WinXP. Windows 7 provides a welcome screen, where one can select between the available user accounts.  
  
 Windows Vista already provided several [options to configure the logon screen](/article/vista-welcome-screen.html), and Windows 7 adds some extra on top.

##### Change logon screen background

 Save the custom background image as **backgroundDefault.jpg** in the following folder (Must be less than 256 KByte in size):
 > %windir%\\system32\\oobe\\info\\backgrounds

 Then activate loading of OEM background image with this DWORD registry key:
 > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Authentication \\LogonUI \\Background\]  
 >  OEMBackground = 1

 Credits [WithInWindows.com](http://www.withinwindows.com/2009/03/15/windows-7-to-officially-support-logon-ui-background-customization/)