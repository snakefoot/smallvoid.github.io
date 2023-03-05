---
title: 'Repair Internet Explorer when it is no longer working'
date: '2001-01-01T23:35:19+01:00'
status: publish
permalink: /article/repair-internet-explorer.html
author: Snakefoot
excerpt: 'Different steps for how to fix a broken Internet Explorer.'
type: post
id: 245
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - system-recovery
post_format: []
tags:
    - system-recovery
---
Internet Explorer (IE) can become corrupted, so it no longer works. This usually means that one have to reinstall IE, or worse reinstall Microsoft Windows from scratch (Since it is an integrated part of the operating system). Before exploring these extreme measures, then one should check the following steps, as they might be able to solve whatever issues IE has:

- **Empty Temporary Internet Files cache**  
   The database which controls the Temporary Internet Files can go corrupt. The effect will be considerable slow downs and extensive usage of the CPU. A broken file cache can also block Internet Explorer from saving images in other formats than BMP. To solve this one need to clear this file cache.  
    
  [Clear the Temporary Internet Files cache](/article/ie-temporary-internet-files.html)  
    
   More info [MS KB260650](http://support.microsoft.com/kb/260650 "Internet Explorer Does Not Save Graphics Files in the Proper Format [Q260650]")
- **Delete the cookies**  
   Cookies are used by websites to identify you and might be used for storing passwords or spying on your actions. Cookies can become corrupted and affect the access to a web-site. Only solution is to delete the corrupted cookies, which can be located in the directory containing [Temporary Internet Files](/article/ie-temporary-internet-files.html)
- **Restore Internet-Security-Policy to default :**  
   Control Panel -&gt; Internet Options -&gt; Security-tab -&gt; Select "Internet" -&gt; Press "Default Level"-button
- **Restore Internet Explorer Options to default :**  
   Control Panel -&gt; Internet Options -&gt; Advanced-tab -&gt; Press "Restore Defaults"-button  
    
   Note one might want to consider in a repair situation to uncheck "Enable third-party browser extensions (requires restart)" to disable funny 3rd party plugins, but it will also keep other valid programs from integrating with Internet Explorer.  
    
   More info [MS KB298931](http://support.microsoft.com/kb/298931 "How to Disable Third-Party Tool Bands and Browser Helper Objects [Q298931]")
- **Restore Internet Explorer as the default browser :**  
   Control Panel -&gt; Internet Options -&gt; Programs-tab -&gt; Tick "Internet Explorer should check to see if it is the default" and press Apply-button  
    
   More info [MS KB177054](http://support.microsoft.com/kb/177054 "OLEXP: Internet Shortcuts in Outlook Express Do Not Start Web Browser [Q177054]")
- **Restore the toolbars:**  
   Use the registry editor (regedit) to delete the following values (Perform an export first):
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar \\Explorer\]  
  > **ITBarLayout** = ?  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar \\ShellBrowser\]  
  > **ITBarLayout** = ?  
  >   
  >  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Toolbar \\WebBrowser\]  
  > **ITBarLayout** = ?
- **Scan computer for Adware and Spyware:**  
   Spyware/Adware can lock up your browser or reset your default homepage.  
    
  [Windows Live - Safety Center](http://safety.live.com/) (Online automated tool by Microsoft)  
  [Lavasoft Ad-Aware](http://www.lsfileserv.com/) (Automated Tool)  
  [Spybot - Search &amp; Destroy](http://spybot.eon.net.au/) (Automated Tool)  
  [Merijn - HijackThis](http://www.spywareinfo.com/~merijn/downloads.html) (Manual detection and cleanup)  
  [BHODemon](http://www.definitivesolutions.com/bhodemon.htm) (Manual detection and cleanup)  
    
   Note one should also check for other 3rd Party software (Ex. Browser Helper Objects), which might "integrate" with Internet Explorer (Ex. popup stoppers), check Add/Remove Programs in Control Panel and uninstall anything that might affect Internet Explorer.  
    
   More info [MS KB320159](http://support.microsoft.com/kb/320159 "Home Page Setting Changes Unexpectedly, or You Cannot Change Your Home Page Setting [Q320159]")
- **Check that the HOSTS file do not contain any extra entries**  
   If having trouble accessing certain sites or pictures, then it might be caused by the [hosts file](/article/windows-hosts-file.html) blocking access. Check that it only contains a single entry "127.0.0.1 localhost".
- **Check if firewall or antivirus is blocking access :**  
   If disabling the firewall/antivirus makes things work, then it is probably a good idea to reinstall those.
- **Re-Install Windows Scripting Engine :**  
   Download the Windows Script-package that matches your Windows version. 
  - [Windows Script 5.6 for Windows 98, Windows Me, and Windows NT 4.0](http://www.microsoft.com/downloads/details.aspx?FamilyID=0a8a18f6-249c-4a72-bfcf-fc6af26dc390) ([Mirror of scr56en.exe](http://smallvoid.orgfree.com/?file=scr56en.zip "Windows9x-Script56-KB917344-x86-enu.exe"))
  - [Windows Script 5.6 for Windows 2000](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=C717D943-7E4B-4622-86EB-95A22B832CAA)
  - [Windows Script 5.7 for Windows XP](http://www.microsoft.com/downloads/details.aspx?FamilyID=47809025-D896-482E-A0D6-524E7E844D81)
  - [Windows Script 5.6 for Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?FamilyID=887fce82-e3f5-4289-a5e3-6cbb818623aa)
- **Re-Register some DLLs which IE uses :**  
   Close all instances of IE and open a Command-prompt or use Start-Button -&gt; Run.. to execute each of the below lines. (Note shell32.dll is only used in Win2k/XP)  
  > regsvr32 Shell32.dll  
  >  regsvr32 Shdocvw.dll  
  >  regsvr32 Oleaut32.dll  
  >  regsvr32 Ole32.dll  
  >  regsvr32 Actxprxy.dll  
  >  regsvr32 Mshtml.dll  
  >  regsvr32 Urlmon.dll  
  >  regsvr32 Inseng.dll  
  >  regsvr32 Browseui.dll  
  >  regsvr32 Msjava.dll  
  >  regsvr32 Jscript.dll  
  >  regsvr32 mobsync.dll
  
   Note if using WinXP SP2 then one can just run this command:
  > "%ProgramFiles%\\Internet Explorer\\iexplore.exe" /rereg  
  >   
  >  More Info [MS KB870700](http://support.microsoft.com/kb/870700 "How to troubleshoot problems accessing secure Web pages with Internet Explorer 6 Service Pack 2 [Q870700]")
  
   More Info [MS KB180176](http://support.microsoft.com/kb/180176 "'Open in New Window' Command Does Not Work in Internet Explorer [Q180176]")  
   More Info [MS KB281679](http://support.microsoft.com/kb/281679 "You Cannot Open New Internet Explorer Window or Nothing Happens After You Click a Link [Q281679]") (Previous MS KB272322)
- **Try the IE Repair Tool**  
   There is a repair function in Internet Explorer(IE) which can check if you have gotten incorrect files installed or wrong registry entries.  
    
   If you have installed IE then you should be able to activate the repair tool by entering "Add/Remove Programs" in the control panel. There you can select the IE installation and press Change. This pops up window which among things allow you to repair your IE.  
    
   If having IE installed without having such entry in your "Add/Remove Programs" list then you can also activate it. Press the Start Button and select "Run..." and execute this line:  
    
   If using IE5+ :  
   > rundll32 setupwbv.dll,IE5Maintenance "C:\\Program Files\\Internet Explorer\\Setup\\SETUP.EXE" /g "%WINDIR%\\IE Uninstall Log.Txt"
  
   If using IE6+ :
   > rundll32 setupwbv.dll,IE6Maintenance "C:\\Program Files\\Internet Explorer\\Setup\\SETUP.EXE" /g "%WINDIR%\\IE Uninstall Log.Txt"
  
   The result of your repair is logged in this file "Fix IE Log.txt" which is created in your Windows folder.  
    
   In WinXP the IE Repair tool doesn't work, one can instead try to [Reinstall IE](/article/winnt-reinstall-ie.html).  
    
   More info [MS KB194177](http://support.microsoft.com/kb/194177 "Description of the Internet Explorer Repair Tool for IE5 [Q194177]")  
   More info [MS KB236579](http://support.microsoft.com/kb/236579 "The Repair Internet Explorer Tool Is Missing [Q236579]")
- **Restore some DLLs which IE uses :**  
  > Shdocvw.dll  
  >  Shell32.dll  
  >  Oleaut32.dll  
  >  Actxprxy.dll  
  >  Mshtml.dll  
  >  Urlmon.dll  
  >  Inseng.dll  
  >  Browseui.dll
  
   More Info [MS KB321915](http://support.microsoft.com/kb/321915 ""Incompatible Version of the RPC Stub" Error Message with the InstallShield Program [Q321915]") (mcrepair.exe)  
    
   Related [Use extract.exe to restore a system file in Win9x/Me](/article/win9x-extract-restore.html)  
   Related [The System File Checker in Win2k/WinXP](/article/winnt-sfc.html)
 
 More Info [How to fix the top 10 Internet Explorer issues](http://www.microsoft.com/windows/ie/community/columns/ietopten.mspx "It's not always malware: How to fix the top 10 Internet Explorer issues by Sandi Hardmeier")  
  
 Credits [Sandi's Site](http://www.mvps.org/inetexplorer/)