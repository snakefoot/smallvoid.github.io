---
title: 'Configuration of the boot manager entries'
date: '2007-10-30T01:04:04+01:00'
status: publish
permalink: /article/winnt-bootmgr-config.html
author: Snakefoot
excerpt: 'Description of the Boot Configuration Data (BCD) used to store the configuration of the boot manager.'
type: post
id: 755
category:
    - Troubleshoot
tag:
    - boot-manager
post_format: []
tags:
    - boot-manager
---
Windows Vista includes a new Boot Manager (BootMgr) that replaces the old [NT Loader](/article/winnt-update-boot-manager.html) (Ntldr) and its configuration text file [boot.ini](/article/winnt-boot-ini.html).  
  
 Instead of using a normal text editor to configure the boot manager, then Microsoft have created the tool BCDEdit.exe, which is a command line tool for updating the Boot Configuration Data (BCD) registry at \\BOOT\\BCD.  
  
 To backup / restore the existing BCD in case something should go wrong:
> Bcdedit /export C:\\BCD\_Backup  
>   
> Bcdedit /import C:\\BCD\_Backup

 To set an option using BCDEdit:
 > BCDEdit /SET \[id\] datatype value
> 
> - **\[id\]** - Is optional and specifies the GUID of the boot entry. If not specified then it will use the active GUID. To see all ids run this command **BCDEdit /enum**.

 List of some of the different datatype configuration switches available. More Info [MS MSDN](http://msdn2.microsoft.com/en-us/library/aa906211.aspx "BCD Boot Options Reference"):
- **bootlog** - Yes / No  
   Enables the system initialization log.
- **hal** - filename  
   Use a different [Hardware Abstraction Layer](/article/winnt-hardware-abstraction-layer.html) (HAL). The HAL file must reside in the %SystemRoot%\\system32 directory and conform to the 8.3 format. Useful if wanting switch between multi- and single-processor HAL.
- **increaseuserva** - megabytes  
   Changes how the kernel and user memory area is divided. By default the size of each is 2 GByte, but this settings allows one to increase the size of the user memory area, so the kernel area becomes 4 GByte substracted the given value (must be between 2048 and 3072).
- **kernel** - filename  
   Use a different kernel in case needing to debug a driver using a checked kernel with debug symbols. The kernel file must reside in the %SystemRoot%\\system32 directory and conform to the 8.3 format.
- **nolowmem** - on / off  
   When turned on then it will load operating system, device drivers, and all applications into addresses above the 4 GB boundary, and directs Windows to allocate all memory pools at addresses above the 4 GB boundary (Useful for testing drivers).
- **nx** - Optin / OptOut / AlwaysOn / AlwaysOff  
   Configures Data Execution Prevention (DEP) which prevents executing of code that resides in areas markes as data. More Info [Windows Help](http://windowshelp.microsoft.com/Windows/en-US/Help/1d9bb9b4-f6ba-466d-ac2b-7b8c4f8361611033.mspx): 
  - **OptIn** (Default policy) - all Windows system binaries are covered by DEP, and it is possible to activate DEP for certain 3rd party applications.
  - **OptOut** - All Windows system binaries are covered by DEP along with 3rd party applications, and it is possible to exclude 3rd party application from being covered by DEP.
  - **AlwaysOn** - Forces all applications to be covered by DEP.
  - **AlwaysOff** - Disables DEP and it can be useful if having installed an application that activates DEP, but killing the application keeps the machine from booting properly.
- **onecpu** - on / off  
   Forces only the boot CPU to be used in a computer that has more than one logical processor.
- **pae** - Default / ForceEnable / ForceDisable  
   Enables Physical Address Extensions (PAE) which means that it extends the use of the CPU memory registers from 32 bit to 36 bit and allows it to address up to 64 GByte RAM. By default PAE is disabled unless DEP is activated. More Info [MS KB929605](http://support.microsoft.com/kb/929605 "The system memory that is reported in the System Information dialog box in Windows Vista is less than you expect if 4 GB of RAM is installed")
- **quietboot** - on / off  
   Controls the display of a high-resolution bitmap in place of the Windows boot screen display and animation. This picture is located in the system file "winload.exe.mui" and the picture is called "Aurora". To change the picture, then one has to replace the system file with another.
- **removememory** - Megabytes  
   Removes memory from the total available memory that the operating system can use.
- **sos** - on / off  
   When turned on it will display the names of the drivers as they load during the boot process.
- **truncatememory** - address  
   Limits the amount of physical memory available to Windows. When you use this option, Windows ignores all memory at or above the specified physical address. Specify the address in bytes.
- **usefirmwarepcisettings** - yes / no  
   Enables or disables the use of BIOS-configured peripheral component interconnect (PCI) resources.
- **vga** - on / off  
   Forces the use of the default VGA driver.
 
 More Info [WHDC - BCDEdit Commands for Boot Environment](http://www.microsoft.com/whdc/system/platform/firmware/bcdedit_reff.mspx "BCDedit_reff.doc")  
 More Info [Mapping of Boot.ini settings to BCDedit datatypes](http://msdn2.microsoft.com/en-us/library/aa362689.aspx "Mapping Boot Options to Elements")  
  
 There are GUI wrappers around the BCDedit so one doesn't have to fiddle with the command line to change the boot manager configuration. Makes it easy to change the display order, rename entries or change timeout: - Msconfig
- [VistaBootPro](http://www.vistabootpro.org/ "PROnetworks") (Requires .NET)
- [EasyBCD](http://neosmart.net/dl.php?id=1) (Requires .NET)