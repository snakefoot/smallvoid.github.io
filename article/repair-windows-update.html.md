---
title: 'Fix a non-working Windows Update'
date: '2001-04-17T23:28:54+02:00'
status: publish
permalink: /article/repair-windows-update.html
author: Snakefoot
excerpt: 'Possible steps for repairing Windows Update'
type: post
id: 244
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - 'Windows Update'
post_format: []
tags:
    - windows-update
---
There can be several causes for errors when using [windowsupdate.microsoft.com](http://windowsupdate.microsoft.com/)

- If your system date on your computer is not configured correctly to current date, then Windows Update will fail to work.
- If you get a security message about Windows should only be updated by your System Administrator (And you have Administrator Privileges), then you can fix it with setting these DWORD registry keys (or delete them):  
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
  >  DisableWindowsUpdateAccess=0  
  >  NoWindowsUpdate=0 ("Remove links and access to Windows Update")  
  >   
  >  \[HKEY\_LOCAL\_MACHINE \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
  >  DisableWindowsUpdateAccess=0  
  >  NoWindowsUpdate=0  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\WindowsUpdate\]  
  >  DisableWindowsUpdateAccess=0 ("Remove access to use all Windows Update features")
  
   More Info [MS KB283288](http://support.microsoft.com/kb/283288 "WINUP-Err Msg: "Your organization has decided to provide software updates internally rather than through Windows Update. To download updates ..." [Q283288]")  
   More Info [MS KB228548](http://support.microsoft.com/kb/228548 "WINUP-Err Msg: "Windows Update Was Disabled by Your System Administrator" [Q228548]")  
   More Info [MS KB316524](http://support.microsoft.com/kb/316524 ""Administrators Only" Error Message When You Attempt to Use the Windows Update Site [Q316524]")  
   More Info [MS KB326686](http://support.microsoft.com/kb/326686 ""Windows Update Was Disabled by Your System Administrator" Error Message [Q326686]")
- If the Windows Update doesn't load properly at all then you might have answered No to the Trust Certificate. Or the security level in Internet Explorer is set too tough.  
    
   More Info [MS KB174360](http://support.microsoft.com/kb/174360 "How to Use Security Zones in Internet Explorer [Q174360]")  
   More Info [MS KB252829](http://support.microsoft.com/kb/252829 "Trust Provider Warning Message When You Attempt to Gain Access to the Windows Update Web Site [Q252829]")
- If your Internet Explorer is damaged, then it might cause the Windows Update failure.  
    
  [Repair Internet Explorer 5.0+ when its acting weird](/article/repair-internet-explorer.html)
- If there are leftovers from a previously failed update, then it might conflict with the new update. Delete the contents in the following folders:
  > **C:\\Program Files\\WindowsUpdate** (Except the directory **V4** and the file **Wuhistv3.log**)  
  > **C:\\Program Files\\WindowsUpdate\\V4** (Except the file **IUHIST.XML**)  
  > **C:\\WUTemp** (Can be found on another drive depending on free space, note this can make it use mapped network drives unmap these)
  
   More Info [MS KB193385](http://support.microsoft.com/kb/193385 "WINUP: Problems When Viewing or Downloading From Windows Update [Q193385]")  
   More Info [MS KB241122](http://support.microsoft.com/kb/241122 "WINUP: Application Error When You Click Product Updates [Q241122]")  
   More Info [MS KB243787](http://support.microsoft.com/kb/243787 "WINUP: Error Message: Cannot Display Page [Q243787]")
- If the WinXP service [cryptographic service](/article/winnt-services-cryptsvc.html) is disabled, then the WU will fail (It can become disabled if broken database, use link for more detail)
- If Win2k/XP/2k3 DLL files required for running Windows Update needs to be registered (Besides those registered when repairing Internet Explorer):
  > regsvr32.exe regwizc.dll  
  >  regsvr32.exe Mssip32.dll  
  >  regsvr32.exe Wintrust.dll  
  >  regsvr32.exe Softpub.dll  
  >  regsvr32.exe Initpki.dll  
  >  regsvr32.exe Dssenh.dll  
  >  regsvr32.exe Rsaenh.dll  
  >  regsvr32.exe Gpkcsp.dll  
  >  regsvr32.exe Slbcsp.dll  
  >  regsvr32.exe Cryptdlg.dll
  
   For WinXP/2k3 only:
  > regsvr32.exe licdll.dll  
  >  regsvr32.exe Sccbase.dll  
  >  regsvr32.exe Msxml.dll  
  >  regsvr32.exe Msxml2.dll  
  >  regsvr32.exe Msxml3.dll
  
   Note if using WinXP SP2 then one can just run this command:
  > "%ProgramFiles%\\Internet Explorer\\iexplore.exe" /rereg  
  >   
  >  More Info [MS KB870700](http://support.microsoft.com/kb/870700 "How to troubleshoot problems accessing secure Web pages with Internet Explorer 6 Service Pack 2 [Q870700]")
- Look at the trace log created by Windows Update to pin point the cause of failure:
  > %Windir%\\Windows Update.log
- Enable Stepping Mode to diagnose the Windows Update failure. This is done with this STRING registry key:  
  > \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Active Setup\]  
  >  SteppingMode = "Y" (Disabled = "N", ENabled = "Y", Default = "N")
  
   More Info [MS KB178081](http://support.microsoft.com/kb/178081 "Description of the Active Setup Log.txt File [Q178081]")  
   More Info [MS KB248439](http://support.microsoft.com/kb/248439 "WINUP: Using Stepping Mode to Diagnose Download and Installation Failures [Q248439]")
 
 More Info [Reset Windows Update](http://support.microsoft.com/kb/971058 "How do I reset Windows Update components?
")  
 More Info [Windows Update Troubleshooter](http://v4.windowsupdate.microsoft.com/troubleshoot/)  
 More Info [MS KB241234](http://support.microsoft.com/kb/241234 "WINUP-Third-Party Products That Conflict with Windows Update [Q241234]")  
 More Info [MS KB313817](http://support.microsoft.com/kb/313817 "Error Message: Connection Reset by Peer [Q313817]")  
 More Info [MS KB319585](http://support.microsoft.com/kb/319585 "WINUP: "Software Update Incomplete, This Windows Update Software Did Not Update Successfully" Error Message When You Visit the Windows Update Web Site [Q319585]")  
 More Info [MS KB813444](http://support.microsoft.com/kb/813444 "HOW TO: Troubleshoot Situations Where You Cannot Complete MSN Sign-up or Connect to SSL Secured (128-Bit) Web Sites by Using Internet Explorer in Windows XP [Q813444]")  