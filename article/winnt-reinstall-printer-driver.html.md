---
title: 'Reinstall printer drivers in Windows NT'
date: '2004-10-13T00:37:10+02:00'
status: publish
permalink: /article/winnt-reinstall-printer-driver.html
author: Snakefoot
excerpt: 'Changing printer drivers in Windows NT can cause problems, and can require that the old drivers are remove manually first.'
type: post
id: 467
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - drivers
    - printer
post_format: []
tags:
    - 'printer,drivers'
---
If a printer driver haven't been installed properly then it can keep the [Printer Spooler](/article/winnt-services-spooler.html) from starting properly, or cause error messages like:

> *Spooler subsystem app has encountered a problem and needs to close  
>   
>  Operation could not be completed  
>   
>  Spoolsv.exe has generated errors and will be closed by Windows.  
>   
>  Printer operation cannot continue due to lack of resources.  
>   
>  Subsystem unavailable.*

 Normally one can repair this by clearing the [spool directory](/article/winnt-print-spool-folder.html) or doing a reinstall of the printer-drivers, but it can also happen that the existing printer drivers will conflict with the new ones. To avoid the conflict one can try to uninstall all printer drivers:
1. Start the computer in **safemode**, so the printer drivers are not loaded
2. Delete the all files and sub-folders within these two folders: 
  - C:\\Windows\\System32\\Spool\\Printers
  - C:\\Windows\\System32\\Spool\\Drivers\\w32x86
3. Navigate to this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Environment \\Windows NT x86\]  
  >   
  >  Delete all subkeys except:
  > 
  > 
  > - **Drivers**
  > - **Print Processors**
4. Navigate to this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Environment \\Windows NT x86 \\Drivers \\**Version-x**\]  
  >   
  >  The registry entries for the installed printer drivers are stored in subkeys (Ex. **Version-1**). Delete the registry-entries below these sub-keys, but not the sub-keys themselves.
5. Navigate to this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Monitors\]  
  >   
  >  Delete all subkeys except:
  > 
  > 
  > - **AppleTalk Printing Devices** (Might not exist)
  > - **BJ Language Monitor**
  > - **Local Port**
  > - **PJL Language Monitor**
  > - **Standard TCP/IP Port**
  > - **USB Monitor**
  > - **Windows NT Fax Monitor** (Might not exist)
6. Navigate to this registry key:
  > \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Print \\Providers\]  
  >   
  >  Delete all subkeys except:
  > 
  > 
  > - **Internet Print Provider**
  > - **LanMan Print Provider**
7. Navigate to this registry key:
  > \[HKEY\_LOCAL\_MACINE\\SYSTEM \\CurrentControlSet \\Services \\Spooler\]  
  > **DependOnService** = "RPCSS"  
  > **Start** = 2  
  >   
  >  Make sure that **DependOnService** and **Start** are configured as shown above.
8. Disconnect the printer-cable from the computer and do a normal restart
9. When Windows have loaded [verify](/article/winnt-services-config.html) that the Print Spooler has started
10. Reconnect the printer-cable to the computer. Install the printer according to the instructions given by the manufacture.
 
 More Info [MS KB135406](http://support.microsoft.com/kb/135406 "Steps to Manually Remove and Reinstall a Printer Driver [Q135406]")  
 More Info [MS KB312052](http://support.microsoft.com/kb/312052 "Error Message: Spoolsv.exe Has Generated Errors and Will Be Closed by Windows [Q312052]")  
 More Info [MS KB314073](http://support.microsoft.com/kb/314073 "How to Troubleshoot Network Printing Problems in Windows XP [Q314073]")  
 More Info [MS KB324757](http://support.microsoft.com/kb/324757 ""Spooler subsystem app has encountered a problem and needs to close" and "Operation could not be completed" error messages [Q324757]")  
 More Info [MS KB810894](http://support.microsoft.com/kb/810894 "Error message: Spooler subsystem app has encountered a problem and needs to close [Q810894]")  