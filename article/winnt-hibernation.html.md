---
title: 'Disable hibernation to save disk space'
date: '2003-09-17T22:06:02+02:00'
status: publish
permalink: /article/winnt-hibernation.html
author: Snakefoot
excerpt: 'Hibernation requires a file as big as the size of the physical memory, which it dumps the contents of the memory to hibernate.'
type: post
id: 397
category:
    - Tips
    - Tips
tag:
    - free-disk-space
    - hibernation
    - power-management
post_format: []
tags:
    - 'hibernation,power-management,free-disk-space'
---
When using hibernation a snapshot is made of the RAM and saved to the file **C:\\Hiberfil.sys** and the machine is shut down. When restarting again the RAM is restored from the file and is in the same state as before the shutdown. This features can give quick shutdown and restart capabilities (Dependent on HDD speed), but with the expense of used disk space by the file containing the snapshot (Same size as RAM installed)  
  
 Disabling hibernation support to save disk space (WinXP has it enabled by default):

1. Open **Control Panel**
2. Double click **Power Options**
3. Select the **Hibernate**-tab (Only there if all drivers installed supports hibernation)
4. Uncheck **Enable hibernation** (Will remove the file automatically)
 
 More Info [MS KB255182](http://support.microsoft.com/kb/255182 "Hibernate Tab Is Not Available in Power Options Tool in Control Panel [Q255182]")  
 More Info [MS KB293399](http://support.microsoft.com/kb/293399 "HOW TO: How to Manually Enable the Hibernate Feature During an Unattended Install of Windows 2000 [Q293399]")  
 More Info [MS KB308098](http://support.microsoft.com/kb/308098 "HOW TO: Configure a Computer to Enter Hibernation in Windows 2000 [Q308098]")  
 More Info [MS KB308535](http://support.microsoft.com/kb/308535 "Description of the Different Advanced Power Management States [Q308535]")  
  
 Note if having [Clear the Windows Paging File at Shutdown](http://support.microsoft.com/kb/182086 "How to Clear the Windows Paging File at Shutdown [Q182086]") enabled, then the snapshot-file will also be cleared, when shutting down the computer the normal way.  
  
 Note if one gets the following stop error message when the computer enters/leaves hibernation or standby, then one should make sure that the installed hardware/firmware/drivers are up to date:
> Unable to enter Standby mode.  
>   
>  0x0000009F: DRIVER\_POWER\_STATE\_FAILURE  
>   
>  More Info [MS KB197477](http://support.microsoft.com/kb/197477 "The System Cannot Go to Standby Mode Because the... [Q197477]")  
>  More Info [MS KB302414](http://support.microsoft.com/kb/302414 "Unable to Use Power Management Features [Q302414]")  
>  More Info [MS KB305689](http://support.microsoft.com/kb/305689 "Laptop Computer Reaches 100 Percent CPU Usage After You Remove It from the Docking Station [Q305689]")  
>  More Info [MS KB305905](http://support.microsoft.com/kb/305905 "Hibernation Does Not Work on a Portable Computer After Windows XP Upgrade and RAM Increase [Q305905]")  
>  More Info [MS KB315249](http://support.microsoft.com/kb/315249 "Troubleshooting a Stop 0x9F Error in Windows XP [Q315249]")  
>  More Info [MS KB907477](http://support.microsoft.com/kb/907477 "How to troubleshoot hibernation and standby issues in Windows XP [Q907477]")

 Note if wanting to use hibernation in WinXP and one selects "Turn off computer" it only shows "Stand by"-, "Turn Off"- and "Restart"-buttons (Non-Classic). One have to press down the Shift-key and it will change "Stand by" to "Hibernate". More Info [MS KB291790](http://support.microsoft.com/kb/291790 " [Q291790]")  
  
 Note if entering hibernation through CTRL+ALT+DEL in WinXP, then when resuming the shell is not restored because the explorer.exe is not in memory when hiberfil.sys is created. To prevent this behavior disable [Use the Welcome Screen](/article/winxp-welcome-screen.html). More Info [MS KB833161](http://support.microsoft.com/kb/833161 "Windows Explorer Does Not Start After Resuming From Hibernation [Q833161]")  
  
 Note in WinXP SP1 and Win2k3 a command line tool was released that presents more Power Management options than the "Power Options"-applet in the Control Panel. > powercfg /?  
>   
>  More Info [MS KB324347](http://support.microsoft.com/kb/324347 "How to Use Powercfg.exe in Windows Server 2003 [Q324347]")