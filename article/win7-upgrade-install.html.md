---
title: 'Perform clean install using Windows 7 upgrade'
date: '2009-10-24T23:34:57+02:00'
status: publish
permalink: /article/win7-upgrade-install.html
author: Snakefoot
excerpt: 'Install Windows 7 using only the upgrade DVD without needing to install it twice.'
type: post
id: 820
category:
    - Tips
tag:
    - windows-install
post_format: []
tags:
    - windows-install
---
Windows 7 can be installed using an upgrade disk, by [installing it twice just as Windows Vista could](/article/vista-upgrade-install.html).  
  
 But there is also a faster way to install Windows 7 using only the upgrade DVD:

1. Perform a clean installation using the Upgrade disc. Now you have a Windows install that is not activated.
2. If there are Windows pending that requires a restart, then reboot first. You'll see an orange shield icon next to Shutdown in the Start Menu if this is the case.
3. Open the registry editor (Regedit.exe) and update the following DWORD registry value:
  > \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Setup \\OOBE\]  
  >  MediaBootInstall = 0
4. Open the command prompt (cmd.exe) in administrator mode, and execute this command:
   > slmgr /rearm
5. Reboot Windows and then launch the Activate Windows utility, and enter your product key. Now Windows is activated without installing it twice.
 
 Credits [Supersite Blog](http://community.winsupersite.com/blogs/paul/archive/2009/10/23/clean-install-windows-7-with-upgrade-media-the-answer.aspx)