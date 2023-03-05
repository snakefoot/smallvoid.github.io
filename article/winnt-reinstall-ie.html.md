---
title: 'Reinstall Internet Explorer in Windows XP'
date: '2002-11-18T23:56:54+01:00'
status: publish
permalink: /article/winnt-reinstall-ie.html
author: Snakefoot
excerpt: 'How to reinstall Internet Explorer in Windows XP.'
type: post
id: 246
category:
    - 'Internet Explorer (IE6)'
tag:
    - install
post_format: []
tags:
    - install
---
Internet Explorer(IE) 6.0 is an integrated part of Windows XP making it very difficult to [Repair](/article/repair-internet-explorer.html) and reinstall. The [System File Protection](/article/winnt-sfc.html) can help sometimes but not always.

- The easy way to reinstall Internet Explorer (Only works in WinXP SP1) 
  1. Quit Internet Explorer and Outlook Express
  2. Open Control Panel -&gt; Add/Remove Programs
  3. Untick "Internet Explorer" and click the "Next"-button and let Internet Explorer be uninstalled
  4. To reinstall again open Control Panel -&gt; Add/Remove Programs and tick "Internet Explorer" and click the "Next"-Button
- Another way to reinstall Internet Explorer is to run this command:
  > rundll32.exe setupapi, InstallHinfSection DefaultInstall 132 %windir%\\inf\\ie.inf
- A third way to reinstall Internet Explorer (Manual version of the above command-line) : 
  1. Quit Internet Explorer and Outlook Express
  2. Using Windows Explorer, open the %SystemRoot%\\Inf folder. (By default, this is the Winnt\\Inf folder or Windows\\Inf folder)
  3. In the menu Tools -&gt; Folder Options, make sure that "Show hidden files and folders" is ticked and "Hide file extensions for known file types" is cleared
  4. To reinstall Internet Explorer, right click the following file and click "Install"
     > Ie.inf
  5. To reinstall Outlook Express, right click the following file and click "Install"
     > Msoe60.inf
- A fourth way to reinstall Internet Explorer: 
  1. Quit Internet Explorer and Outlook Express
  2. Set the following DWORD registry key to enable reinstall of Internet Explorer
      > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Active Setup \\Installed Components \\{89820200-ECBD-11cf-8B85-00AA005B4383}\]  
      >  IsInstalled = 0 (Default = 1)
  3. Set the following DWORD registry key to enable reinstall of Outlook Express
      > \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Active Setup \\Installed Components \\{44BBA840-CC51-11CF-AAFA-00AA00B6015C}\]  
      >  IsInstalled = 0 (Default = 1)
  4. Start installing [Internet Explorer](http://www.microsoft.com/ie/)
 
 Related [Repair Internet Explorer when its acting weird](/article/repair-internet-explorer.html)  
  
 More Info [MS KB254623](http://support.microsoft.com/kb/254623 "OLEXP: How to Reinstall Microsoft Outlook Express 5 in Windows 2000 [Q254623]")  
 More Info [MS KB263837](http://support.microsoft.com/kb/263837 "How to manually remove and reinstall Outlook Express [Q263837]")  
 More Info [MS KB293907](http://support.microsoft.com/kb/293907 "How to Uninstall Internet Explorer 6 [Q293907]")  
 More Info [MS KB318378](http://support.microsoft.com/kb/318378 "How to Reinstall or Repair Internet Explorer and Outlook Express in Windows XP [Q318378]")  
  
 Credits [help.att.net](http://help.att.net/)