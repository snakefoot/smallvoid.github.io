---
title: 'Install Active Desktop in Windows 95 / NT4'
date: '2003-03-06T23:13:53+01:00'
status: publish
permalink: /article/windows-active-desktop.html
author: Snakefoot
excerpt: 'Installing Active Desktop without needing to install Internet Explorer 4 first.'
type: post
id: 302
category:
    - Desktop
    - Desktop
tag:
    - active-desktop
    - Desktop
    - quick-launch
    - windows-explorer
post_format: []
tags:
    - 'active-desktop,desktop,quick-launch,windows-explorer'
---
Active Desktop is part of the Windows Desktop Update and was introduced with Internet Explorer 4 (IE4). The Active Desktop delivers features like the Quick Launch bar and the ability to dynamically order the Start Menu items. WinNT4 and Win95 doesn't come with IE4 by default, and if one decided to be quick and install IE5 or IE6 without installing IE4 first then Active Desktop isn't installed.  
  
 There are two ways to install the Active Desktop in this situation:

- Uninstall IE? and install IE4 and then install IE? again
- Install the IE4 Active Desktop package on top of the existing IE?
 
 The second solution has the following steps:
1. Download the file (Usually acquired when [downloading IE?](http://www.microsoft.com/windows/ie/downloads/)) 
  - [Ie4shlnt.cab](http://download.microsoft.com/msdownload/ie401/sp2/x86/en/Ie4shlnt.cab) (WinNT4) (Change URL from **EN** to **DA** for Danish)
  - [Ie4shl95.cab](http://download.microsoft.com/msdownload/ie401/sp2/x86/en/Ie4shl95.cab) (Win95) (Change URL from **EN** to **DA** for Danish)
2. Extract the contents of the above cab-file to a directory
3. Right click the now extracted Ie4shell.inf file and select install (Note a background popup might complain about a missing Wallpapr.htm press Ignore)
4. Let it restart your computer
5. Run [The IE Repair Tool](/article/repair-internet-explorer.html) and do a repair (Note your Start Menu, SendTo might not work at this point) 
  - To run a command in WinNT4 press CTRL+SHIFT+ESC to launch Task Manager or browse My Computer to start Winnt\\System32\\cmd.exe
  - To run a command in Win95 press CTRL+ESC to launch Task Manager or browse My Computer to start Windows\\Command.com
6. If icons look garbled then check [Repair incorrectly displayed icons](/article/windows-icon-cache.html)
 
 Note the install of Active Desktop replaces your Explorer.exe with another version (Likely 4.72.3612.1700) and you cannot go back to the old version of the Explorer.exe.  
  
 Note one should make sure that the language of the Active Desktop is the same as the operating system, as mixed binaries can lead to unpredictable results.  
  
 More Info [MS KB165695](http://support.microsoft.com/kb/165695 "How to Add or Remove Windows Desktop Update [Q165695]")  
 More Info [MS KB217344](http://support.microsoft.com/kb/217344 "How to Uninstall Internet Explorer 5 [Q217344]")  
 More Info [MS KB293907](http://support.microsoft.com/kb/293907 "How to Uninstall Internet Explorer 6 [Q293907]")  