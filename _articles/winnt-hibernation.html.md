---
title: 'Disable hibernation to save disk space'
date: '2003-09-17T22:06:02+02:00'
permalink: /article/winnt-hibernation.html
author: Snakefoot
excerpt: 'Hibernation requires a file as big as the size of the physical memory, which it dumps the contents of the memory to hibernate.'
type: post
id: 397
categories:
    - windows-xp_tips
    - windows-2000_tips
tags:
    - free-disk-space
    - hibernation
    - power-management
---
When using hibernation a snapshot is made of the RAM and saved to the file **C:\\Hiberfil.sys** and the machine is shut down. When restarting again the RAM is restored from the file and is in the same state as before the shutdown. This features can give quick shutdown and restart capabilities (Dependent on HDD speed), but with the expense of used disk space by the file containing the snapshot (Same size as RAM installed)  
  
 Disabling hibernation support to save disk space (WinXP has it enabled by default):

1. Open **Control Panel**
2. Double click **Power Options**
3. Select the **Hibernate**-tab (Only there if all drivers installed supports hibernation)
4. Uncheck **Enable hibernation** (Will remove the file automatically)
 
 More Info <a href="https://www.bing.com/search?q=KB+255182+Q255182" rel="nofollow" title="Hibernate Tab Is Not Available in Power Options Tool in Control Panel [Q255182]">MS KB255182</a>  
 More Info <a href="https://www.bing.com/search?q=KB+293399+Q293399" rel="nofollow" title="HOW TO: How to Manually Enable the Hibernate Feature During an Unattended Install of Windows 2000 [Q293399]">MS KB293399</a>  
 More Info <a href="https://www.bing.com/search?q=KB+308098+Q308098" rel="nofollow" title="HOW TO: Configure a Computer to Enter Hibernation in Windows 2000 [Q308098]">MS KB308098</a>  
 More Info <a href="https://www.bing.com/search?q=KB+308535+Q308535" rel="nofollow" title="Description of the Different Advanced Power Management States [Q308535]">MS KB308535</a>  
  
 Note if having <a href="https://www.bing.com/search?q=KB+182086+Q182086" title="How to Clear the Windows Paging File at Shutdown [Q182086]" rel="nofollow">Clear the Windows Paging File at Shutdown</a> enabled, then the snapshot-file will also be cleared, when shutting down the computer the normal way.  
  
 Note if one gets the following stop error message when the computer enters/leaves hibernation or standby, then one should make sure that the installed hardware/firmware/drivers are up to date:
> Unable to enter Standby mode.  
>   
>  0x0000009F: DRIVER\_POWER\_STATE\_FAILURE  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+197477+Q197477" rel="nofollow" title="The System Cannot Go to Standby Mode Because the... [Q197477]">MS KB197477</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+302414+Q302414" rel="nofollow" title="Unable to Use Power Management Features [Q302414]">MS KB302414</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+305689+Q305689" rel="nofollow" title="Laptop Computer Reaches 100 Percent CPU Usage After You Remove It from the Docking Station [Q305689]">MS KB305689</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+305905+Q305905" rel="nofollow" title="Hibernation Does Not Work on a Portable Computer After Windows XP Upgrade and RAM Increase [Q305905]">MS KB305905</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+315249+Q315249" rel="nofollow" title="Troubleshooting a Stop 0x9F Error in Windows XP [Q315249]">MS KB315249</a>  
>  More Info <a href="https://www.bing.com/search?q=KB+907477+Q907477" rel="nofollow" title="How to troubleshoot hibernation and standby issues in Windows XP [Q907477]">MS KB907477</a>

 Note if wanting to use hibernation in WinXP and one selects "Turn off computer" it only shows "Stand by"-, "Turn Off"- and "Restart"-buttons (Non-Classic). One have to press down the Shift-key and it will change "Stand by" to "Hibernate". More Info <a href="https://www.bing.com/search?q=KB+291790+Q291790" rel="nofollow" title=" [Q291790]">MS KB291790</a>  
  
 Note if entering hibernation through CTRL+ALT+DEL in WinXP, then when resuming the shell is not restored because the explorer.exe is not in memory when hiberfil.sys is created. To prevent this behavior disable [Use the Welcome Screen](/article/winxp-welcome-screen.html). More Info <a href="https://www.bing.com/search?q=KB+833161+Q833161" rel="nofollow" title="Windows Explorer Does Not Start After Resuming From Hibernation [Q833161]">MS KB833161</a>  
  
 Note in WinXP SP1 and Win2k3 a command line tool was released that presents more Power Management options than the "Power Options"-applet in the Control Panel.
 > powercfg /?  
>   
>  More Info <a href="https://www.bing.com/search?q=KB+324347+Q324347" rel="nofollow" title="How to Use Powercfg.exe in Windows Server 2003 [Q324347]">MS KB324347</a>