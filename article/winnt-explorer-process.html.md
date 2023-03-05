---
title: 'Use several Explorer.exe processes to increase stability'
date: '2001-02-05T00:05:22+01:00'
status: publish
permalink: /article/winnt-explorer-process.html
author: Snakefoot
excerpt: 'Prevent that all Windows Explorer instances crashes just because one gets a fatal error.'
type: post
id: 374
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - windows-explorer
post_format: []
tags:
    - windows-explorer
---
By default the same Explorer.exe is used to support the Desktop, Taskbar and Folder-views. If one of these get into a bad state or crashes then all of them will fail. This can usually be seen when having to close a Windows Explorer showing folder, as it also closes the desktop (One can just prest CTRL+SHIFT+ESC to launch the Task Manager and start a new task called "explorer" and the desktop will return).  
  
 It is possible to configure that each Folder-view should get their own Explorer.exe process. Create/update this DWORD in the registry:

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  SeparateProcess = 1 (Default=0)  
>   
>  Matches the setting "Launch folder windows in a separate process" in Folder Options.  
>   
>  Note this option is also required if wanting to launch Explorer.exe with different credentials using [RunAs](/article/winnt-services-seclogon.html) though it is not supported by Microsoft (Another option is just to make a copy of Explorer.exe to ex. Xplorer.exe).  
>   
>  More Info [MS KB264728](http://support.microsoft.com/kb/264728 "Windows Explorer in Folders View May Cause Selected Folder to Open in New Window [Q264728]") (Problem with Explorer.exe showing Windows-folder at startup)  
>  More Info [MS KB321942](http://support.microsoft.com/kb/321942 "No Credential Prompt When You Connect to Secure Web Site After You Use Explorer to Start Internet Explorer [Q321942]")  
>  More Info [MS KB817861](http://support.microsoft.com/kb/817861 "Mapped Drives in Windows Explorer May Retain the Name of a Disconnected Drive [Q817861]") (Problem with wrong labels on mapped network drives)

 Note there exists a different option that will enable Desktop and Taskbar to get their own Explorer.exe process, but this option has several annoying side effects (See below). It is intended to be used when debugging the shell, as one doesn't have to stop and start the desktop and taskbar. Create/update this DWORD in the registry:  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  DesktopProcess = 1 (Default=0)  
>   
>  More Info [MS KB156366](http://support.microsoft.com/kb/156366 "How to Run Windows NT Explorer As a Separate Process [Q156366]")  
>  More Info [MS KB181562](http://support.microsoft.com/kb/181562 "Problems Opening or Exploring Folders in Internet Explorer [Q181562]") (Problem when using WinNT4 and IE 4.0/4.01)  
>  More Info [MS KB228502](http://support.microsoft.com/kb/228502 "Windows Explorer Starts When You Start Your Computer [Q228502]") (Problem with Explorer.exe showing Windows-folder at startup)  
>  More Info [MS KB306117](http://support.microsoft.com/kb/306117 "Mapped Drives in Windows Explorer May Retain the Name of a Disconnected Drive [Q306117]") (Problem with wrong labels on mapped network drives)

 Note if launching Internet Explorer (iexplore.exe) inside Explorer (Start -&gt; Run...), then it will re-use the Explorer-process unless separate process have been selected for iexplore:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  BrowseNewProcess = "Yes"  
>   
>  Matches the setting "Launch browser windows in a separate process" on Advanced-tab in Internet Options. With IE 5.01 it is automatically enabled if having more than 32 MByte RAM.  
>   
>  Note if using Windows XP and having set the value to "No", then [Grouping of similar tasks in the taskbar](/article/winnt-taskbar-grouping.html) will put Windows Explorer and Internet Explorer in the same group.  
>   
>  More Info [MS KB175232](http://support.microsoft.com/kb/175232 "Windows Explorer Hangs When Internet Explorer Does [Q175232]")  
>  More Info [MS KB240928](http://support.microsoft.com/kb/240928 ""Launch Browser Windows in a Separate Process" Setting Is Not Available in Internet Explorer 5.01 or Internet Explorer 5.5 [Q240928]")

 Credits [is-it-true.org](http://www.is-it-true.org/)