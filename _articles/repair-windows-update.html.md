---
title: 'Fix a non-working Windows Update'
date: '2001-04-17T23:28:54+02:00'
permalink: /article/repair-windows-update.html
author: Snakefoot
excerpt: 'Possible steps for repairing Windows Update'
type: post
id: 244
categories:
    - windows-2000_troubleshoot
    - windows-2003_troubleshoot
    - windows-98_troubleshoot
    - windows-me_troubleshoot
    - windows-nt4_troubleshoot
    - windows-xp_troubleshoot
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
  
   More Info <a href="https://www.bing.com/search?q=KB+283288+Q283288" rel="nofollow" title="WINUP-Err Msg: 'Your organization has decided to provide software updates internally rather than through Windows Update. To download updates ...' [Q283288]">MS KB283288</a>  
   More Info <a href="https://www.bing.com/search?q=KB+228548+Q228548" rel="nofollow" title="WINUP-Err Msg: 'Windows Update Was Disabled by Your System Administrator' [Q228548]">MS KB228548</a>  
   More Info <a href="https://www.bing.com/search?q=KB+316524+Q316524" rel="nofollow" title="'Administrators Only' Error Message When You Attempt to Use the Windows Update Site [Q316524]">MS KB316524</a>  
   More Info <a href="https://www.bing.com/search?q=KB+326686+Q326686" rel="nofollow" title="'Windows Update Was Disabled by Your System Administrator' Error Message [Q326686]">MS KB326686</a>
- If the Windows Update doesn't load properly at all then you might have answered No to the Trust Certificate. Or the security level in Internet Explorer is set too tough.  
    
   More Info <a href="https://www.bing.com/search?q=KB+174360+Q174360" rel="nofollow" title="How to Use Security Zones in Internet Explorer [Q174360]">MS KB174360</a>  
   More Info <a href="https://www.bing.com/search?q=KB+252829+Q252829" rel="nofollow" title="Trust Provider Warning Message When You Attempt to Gain Access to the Windows Update Web Site [Q252829]">MS KB252829</a>
- If your Internet Explorer is damaged, then it might cause the Windows Update failure.  
    
  [Repair Internet Explorer 5.0+ when its acting weird](/article/repair-internet-explorer.html)
- If there are leftovers from a previously failed update, then it might conflict with the new update. Delete the contents in the following folders:
  > **C:\\Program Files\\WindowsUpdate** (Except the directory **V4** and the file **Wuhistv3.log**)  
  > **C:\\Program Files\\WindowsUpdate\\V4** (Except the file **IUHIST.XML**)  
  > **C:\\WUTemp** (Can be found on another drive depending on free space, note this can make it use mapped network drives unmap these)
  
   More Info <a href="https://www.bing.com/search?q=KB+193385+Q193385" rel="nofollow" title="WINUP: Problems When Viewing or Downloading From Windows Update [Q193385]">MS KB193385</a>  
   More Info <a href="https://www.bing.com/search?q=KB+241122+Q241122" rel="nofollow" title="WINUP: Application Error When You Click Product Updates [Q241122]">MS KB241122</a>  
   More Info <a href="https://www.bing.com/search?q=KB+243787+Q243787" rel="nofollow" title="WINUP: Error Message: Cannot Display Page [Q243787]">MS KB243787</a>
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
  >  More Info <a href="https://www.bing.com/search?q=KB+870700+Q870700" rel="nofollow" title="How to troubleshoot problems accessing secure Web pages with Internet Explorer 6 Service Pack 2 [Q870700]">MS KB870700</a>
- Look at the trace log created by Windows Update to pin point the cause of failure:
  > %Windir%\\Windows Update.log
- Enable Stepping Mode to diagnose the Windows Update failure. This is done with this STRING registry key:  
  > \[HKEY\_LOCAL\_MACHINE\\ Software\\ Microsoft\\ Active Setup\]  
  >  SteppingMode = "Y" (Disabled = "N", ENabled = "Y", Default = "N")
  
   More Info <a href="https://www.bing.com/search?q=KB+178081+Q178081" rel="nofollow" title="Description of the Active Setup Log.txt File [Q178081]">MS KB178081</a>  
   More Info <a href="https://www.bing.com/search?q=KB+248439+Q248439" rel="nofollow" title="WINUP: Using Stepping Mode to Diagnose Download and Installation Failures [Q248439]">MS KB248439</a>
 
 More Info <a href="https://www.bing.com/search?q=KB+971058+Q971058" title="How do I reset Windows Update components?" rel="nofollow">Reset Windows Update</a>  
 More Info [Windows Update Troubleshooter](http://v4.windowsupdate.microsoft.com/troubleshoot/)  
 More Info <a href="https://www.bing.com/search?q=KB+241234+Q241234" rel="nofollow" title="WINUP-Third-Party Products That Conflict with Windows Update [Q241234]">MS KB241234</a>  
 More Info <a href="https://www.bing.com/search?q=KB+313817+Q313817" rel="nofollow" title="Error Message: Connection Reset by Peer [Q313817]">MS KB313817</a>  
 More Info <a href="https://www.bing.com/search?q=KB+319585+Q319585" rel="nofollow" title="WINUP: 'Software Update Incomplete, This Windows Update Software Did Not Update Successfully' Error Message When You Visit the Windows Update Web Site [Q319585]">MS KB319585</a>  
 More Info <a href="https://www.bing.com/search?q=KB+813444+Q813444" rel="nofollow" title="HOW TO: Troubleshoot Situations Where You Cannot Complete MSN Sign-up or Connect to SSL Secured (128-Bit) Web Sites by Using Internet Explorer in Windows XP [Q813444]">MS KB813444</a>  