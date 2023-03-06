---
title: 'Boot.ini switches used by the Boot Manager'
date: '2000-01-01T00:42:31+01:00'
status: publish
permalink: /article/winnt-boot-ini.html
author: Snakefoot
excerpt: 'Boot.ini is used by the Boot Manager to determine the installed operating systems and what startup settings to use.'
type: post
id: 251
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - boot-ini
    - boot-manager
post_format: []
tags:
    - 'boot-ini,boot-manager'
---
The BOOT.INI file is placed in the root of the system drive ex. C:\\BOOT.INI (One have to turn on "Show Hidden Files and folders" to see it). It is a standard text-file and can be edited with a text-editor like notepad.  
 The BOOT.INI tells the WinNT bootmanager what operating systems that are available, and what switches to use when starting a WinNT+ operating system.  
  
 Starting switches for WinNT 4 and beyond:

- <a name="BOOT_INI_3GB"></a>**/3GB** - Enables 4 GT RAM tuning, where [kernel memory](/article/winnt-kernel-memory.html) is limited to 1 GB and user memory is increased to 3 GB, instead of 2 GB each. By limiting the kernel area, then one will limit Page Table Entries (PTEs) to 40,000 (Instead of 80.000-140.000) along with paged- and non-paged-pool being limited. (Will limit the access to physical memory to 16 GByte RAM).  
    
   This setting is available in the following operating systems: 
  - Windows XP Professional
  - Windows Server 2003
  - Windows 2000 Advanced- and DataCenter-Edition only
  - Windows NT Server 4.0 SP3 Enterprise-Edition only
   
   More Info [MS KB171793](http://support.microsoft.com/kb/171793 "Information on Application Use of 4GT RAM Tuning [Q171793]") [MS KB328882](http://support.microsoft.com/kb/328882 "Exchange memory use and the /3GB switch [Q328882]"), [WHDC - Windows Memory Support](http://www.microsoft.com/whdc/system/platform/server/PAE/PAEmem.mspx "Memory Support and Windows Operating Systems").  
   The [/USERVA](#BOOT_INI_USERVA) setting can be used to increase the 1 GByte kernel memory limit.
- **/BASEVIDEO** - Forces the system into standard 640x480 16-color VGA mode. This is the default on the second boot menu entry. It is useful if having installed a video driver that won't boot or display properly. It is also useful if the graphics hardware is hogging [memory address space](/article/winnt-kernel-memory.html). More Info [MS KB139615](http://support.microsoft.com/kb/139615 "Blank Screen May Be Caused By Corrupt Video Driver [Q139615]"), [MS KB2001745](http://support.microsoft.com/kb/2001745 "Working Set Trimming can negatively impact SQL, Exchange, and Operating System performance under Windows 2003")
- **/BAUDRATE=nnnn** - Sets baudrate of the debug port. If you do not set the baud rate, the default baud rate is 19,200. 9,600 is the normal rate for remote debugging over a modem. This will also enable the /DEBUG switch.
- **/BREAK** - Causes the HAL to stop at a breakpoint at HAL initialization, which is the first thing to be initialized at kernel initialization. And waits until a debugger connection is made. If used without the /DEBUG switch it will cause a BSOD with STOP code of 0x00000078 (PHASE0\_EXCEPTION)
- **/BURNMEMORY=number** - Tells NT to exclude a certain amount of the system memory. The number is given in MegaBytes.
- **/CRASHDEBUG** - Enables the COM port for debugging if Windows NT crashes, but allows you to use the COM port for normal operations. More Info [MS KB151981](http://support.microsoft.com/kb/151981 "How to Set Up a Remote Debug Session Using a Null Modem Cable (MS KB151981) [Q151981]") More Info [MS KB148954](http://support.microsoft.com/kb/148954 "How to Set Up a Remote Debug Session Using a Modem [Q148954]")
- **/DEBUG** - Enables the kernel debugger. This allows live remote debugging of a Windows NT system through the COM ports. Unlike /CRASHDEBUG, /DEBUG will use the COM port whether or not you are debugging. More Info [MS KB121543](http://support.microsoft.com/kb/121543 "Setting Up for Remote Debugging (MS KB121543) [Q121543]")
- **/DEBUGPORT=comx** - Selects a COM port for the debug port. The default is COM2 if it exists, otherwise the default is COM1. The default of COM2 is probably because the [UPS Service](/article/winnt-services-ups.html) claims COM1 when running.
- **/KERNEL=filename** - allows you to define the actual KERNEL to be loaded at startup. This is useful if wanting to test drivers with a checked kernel with debug symbols. This can also be used to load a different ntoskrnl.exe with a different [boot screen](/article/xp-visual-style.html) without conflicting with [WFP](/article/winnt-wfp.html).
- **/HAL=filename** - Defines the actual [Hardware Abstraction Layer](/article/winnt-hardware-abstraction-layer.html) (HAL) to be loaded at startup. This switch is useful in trying out an different HAL before renaming it to hal.dll. This switch is also useful when you want to try booting between multiprocessor and single processor mode when used in conjunction with the /KERNEL switch
- **/MAXMEM=** - The number of megabytes of RAM that NT should see. Must be less than or equal to the actual RAM. This can be useful for special software like RAM drive which doesn't want WinNT to control the RAM. More Info [MS KB108393](http://support.microsoft.com/kb/108393 "MAXMEM Option in Windows NT BOOT.INI File [Q108393]") [MS KB241289](http://support.microsoft.com/kb/241289 "How to Change the Amount of Memory Used During an Installation [Q241289]") [MS KB320286](http://support.microsoft.com/kb/320286 "Access Violation Occurs When You Use the /MAXMEM Start Switch on 64-bit Versions of Windows Server 2003 on Computers That Have More Than 4GB of RAM [Q320286]")
- **/NODEBUG** - Disables the kernel debugger, causing a blue screen if a piece of code has a debug hardcoded breakpoint in its software.
- **/NOSERIALMICE:COMx** - Disables the mouse port check for this com port. Ports may be separated with commas to disable more than one port. If no serial port is specified then ALL ports will be disabled for mouse devices. If you have a UPS on COM1, you would use /NOSERIALMICE:COM1. More Info [MS KB131976](http://support.microsoft.com/kb/131976 "How to Disable Detection of Devices on Serial Ports [Q131976]")
- **/NUMPROC=n** - Sets the number of processors that Windows NT will use in a multiprocessor environment. This is useful in load simulation. If you use this switch.
- **/ONECPU** - Tells Windows NT to use only 1 CPU in a multiprocessor/multicore environment.
- **/PCILOCK** - Prevents Windows NT from enumerating(assigning IO/IRQ Resources) the PCI bus every time it starts. But uses the setup by BIOS. More Info [MS KB148501](http://support.microsoft.com/kb/148501 "Preventing PCI Resource Conflicts on Intel-Based Computers [Q148501]")
- **/SOS** - Causes the loader to print the name of loaded modules/drivers instead of displaying the dots. (In Win2k+ it works best combined with the option NOGUIBOOT)
- **/USE8254** - Forces the HAL to use the 8254 timer chip as base timer. Intended for older BIOS's. More Info [MS KB169901](http://support.microsoft.com/kb/169901 "Perfmon: Processor Spikes on Multiprocessor Computer (MS KB169901) [Q169901]")
- **/WIN95** - Loads bootsec.dos - for triple booting WinNT/9x/DOS. More Info [MS KB157992](http://support.microsoft.com/kb/157992 "How to Triple Boot to Windows NT, Windows 95/98, and MS-DOS (MS KB157992) [Q157992]")
- **/WIN95DOS** - Loads bootsec.w40 - for triple booting WinNT/9x/DOS. More Info [MS KB157992](http://support.microsoft.com/kb/157992 "How to Triple Boot to Windows NT, Windows 95/98, and MS-DOS (MS KB157992) [Q157992]")
- **/YEAR=year** - Tells WinNT to ignore the system year in the BIOS but use the year given. (Only available on WinNT SP4 and beyond)
 
 Starting switches for Win2k and beyond:
- **/BOOTLOG** - Will create a log %SystemRoot%\\NTBTLOG.TXT specifying what modules and drivers are loaded during boot.
- **/FASTDETECT** - Tells Ntdetect.com to Skips enumeration of parallel and serial devices. More Info [MS KB227991](http://support.microsoft.com/kb/227991 "Bus Mouse Does Not Function with /Fastdetect Switch in Boot.ini File [Q227991]")
- **/INTAFFINITY** - In a multiprocessor environment it will direct the HAL (HALMPS.DLL) only to give interrupts to the highest numbered processor.
- **/MAXPROCSPERCLUSTER=** - In a multiprocessor environment it will direct the HAL (HALMPS.DLL) to create clusters of CPUs to make several CPUs act together as a single CPU. Default is 0 and max is 4.
- **/NOGUIBOOT** - This will disable the VGA video driver used at boot time. This will cause it not to show boot progress information aswell as BSOD if such should happen. But it will speed up the bootup time.
- **/NOLOWMEM** - Will disable use of the first 4 GByte. The system must have more than 4 GByte and it can only be used together with the /PAE switch. This is useful when combined with the registry setting "AllocationPreference" when wanting to test if a large memory aware application is actually capable of handling memory addresses beyond the 2 GByte barrier. More Info [MS KB291988](http://support.microsoft.com/kb/291988 "A Description of the 4 GB RAM Tuning Feature and the Physical Address Extension Switch [Q291988]")
- **/NOPAE** - Disables use of /PAE even if the system supports it and have more than 4 GByte of system memory
- <a name="BOOT_INI_PAE"></a>**/PAE** - Enables use of memory beyond 4 GByte by telling NTLDR to load Ntkrnlpa.exe. Intel has created something called Physical Address Extensions(PAE) which extends the use of the CPU memory registers from 32 bit to 36 bit, and alllows it to address up to 64 GByte of system memory. More Info [MS KB291988](http://support.microsoft.com/kb/291988 "A Description of the 4 GB RAM Tuning Feature and the Physical Address Extension Switch [Q291988]") [MS KB283037](http://support.microsoft.com/kb/283037 "Large Memory Support Is Available in Windows 2000 and Windows Server 2003 [Q283037]") [MS KB268363](http://support.microsoft.com/kb/268363 "Intel Physical Addressing Extensions (PAE) in Windows 2000 [Q268363]") [MS KB311901](http://support.microsoft.com/kb/311901 "The Effects of 4GT Tuning on System Page Table Entries [Q311901]") [MS KB888137](http://support.microsoft.com/kb/888137 "The amount of RAM reported by the System Properties dialog box and the System Information tool is less than you expect after you install Windows XP Service Pack 2 [Q888137]") [MS WHDC - PAE](http://www.microsoft.com/whdc/system/platform/server/PAE/PAEdrv.mspx "Physical Address Extension - PAE Memory and Windows")   
    
   The limit of possible memory depends on the Windows version: <table border="1"><tr><th>Windows</th><th>Max Limit</th></tr><tr><td>Windows XP Professional</td><td>4 GByte</td></tr><tr><td>Windows 2000/2003 Server</td><td>4 GByte</td></tr><tr><td>Windows 2000 Advanced Server</td><td>8 GByte</td></tr><tr><td>Windows 2003 Enterprise Server</td><td>32 GByte</td></tr><tr><td>Windows 2000/2003 DataCenter Server</td><td>64 GByte</td></tr><tr><td>Windows 2000/2003 DataCenter Server (+ /3GB)</td><td>16 GByte</td></tr><tr><td>Windows 2003 **SP1** Enterprise Server</td><td>64 GByte</td></tr><tr><td>Windows 2003 **SP1** DataCenter Server</td><td>128 GByte</td></tr><tr><td>Windows 2003 **SP1** DataCenter Server (+ /3GB)</td><td>64 GByte</td></tr></table>
- **/TIMERES=number** - Specifies the resolution of the system timer in a multiprocessor environment. The number is 100s of nanoseconds, the supported values is 9766, 19532, 39063, 78125.
- **/SAFEBOOT:**parameter - To access safemode features. More Info [MS KB239780](http://support.microsoft.com/kb/239780 "Safe-Mode Boot Switches for Windows Boot.ini File [Q239780]")
  - **minimal** - Booting in safemode only loading the drivers and services specified at:
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Safeboot \\Minimal\]
  - **network** - Booting in safemode with network support only loading the drivers and services specified at:
  > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Safeboot \\Network\]
  - **minimal(alternateshell)** - Instead of using explorer.exe it uses the shell specified at (If none specified it uses CMD.EXE):
    > \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\Safeboot\]  
    >  AlternateShell = ""
  - **dsrepair** - Directory Services Repair mode is used when wanting to restore the Active Directory on a domain controller from a backup medium you present. It can also be used if wanting to measure the correct size of the Active Directory Database. It can also be used if wanting to defrag the Ntds.dit using Ntdsutil.exe. More Info [MS KB229602](http://support.microsoft.com/kb/229602 "Defragmentation of the Active Directory Database [Q229602]"), [MS KB816120](http://support.microsoft.com/kb/816120 "HOW TO: Use Ntdsutil to Manage Active Directory Files from the Command Line in Windows Server 2003 [Q816120]")
 
 Starting switches for WinXP/Win2k3 and beyond:
- <a name="BOOTLOGO"></a>**/BOOTLOGO** - When combined with /NOGUIBOOT then it will load the optional bootlogo file boot.bmp(640x480 16 color) located in the Windows-directory.
- <a name="BOOT_INI_USERVA"></a>**/USERVA** - Enables fine tuning of how the user- and [kernel-memory area](/article/winnt-kernel-memory.html) is divided. Used in combination with [/3GB](#BOOT_INI_3GB). More Info [MS KB316739](http://support.microsoft.com/kb/316739 "How to Use the /USERVA Switch in the Boot.ini File to Tune /3GB Configurations [Q316739]")
- **/REDIRECT** - Enables Emergency Management Services (EMS)
- **/CHANNEL** - Enables debugging using a 1394 port
- **/NOEXECUTE=**policy - To configure Data Execution Prevention (DEP), which is available in AMD 64 bit processors, and is by default enabled. More Info [MS KB875352](http://support.microsoft.com/kb/875352 "A detailed description of the Data Execution Prevention (DEP) feature in Windows XP Service Pack 2 and Windows XP Tablet PC Edition 2005 [Q875352]") [MS Technet](http://www.microsoft.com/technet/security/prodtech/windowsxp/depcnfxp.mspx "How to Configure Memory Protection in Windows XP SP2")
  - **OptIn** Default policy; all Windows system binaries are covered by DEP, and it is possible to activate DEP for certain 3rd party applications.
  - **OptOut** All Windows system binaries are covered by DEP along with 3rd party applications, and it is possible to exclude 3rd party application from being covered by DEP.
  - **AlwaysOn** Forces all applications to be covered by DEP
  - **AlwaysOff** Disables DEP and it can be useful if having installed an application that activates DEP, but killing the application keeps the machine from booting properly. More Info [MS KB878474](http://support.microsoft.com/kb/878474 "Your computer repeatedly restarts after you install Windows XP Service Pack 2 [Q878474]"), [MS KB886348](http://support.microsoft.com/kb/886348 "You receive a Stop error when a driver is not compatible with the Data Execution Prevention (DEP) feature in Windows XP SP2 [Q886348]")
- **/USEPMTIMER** - Forces the [Hardware Abstraction Layer](/article/winnt-hardware-abstraction-layer.html) (HAL) to use ACPI Power Management Timer (PMTimer/PMT) as the constant High Resolution Timer (HRT) to generate clock interupts. Instead of using the Real Time Clock (RTC) or the 8254 Programmable Interval Timer (PIT). The AMD driver for the X2 dual core processor adds this setting, because the default processor timestamp-counter (TSC) is not synchronized properly between cores, and causes certain applications to run at double speed. More Info [MS KB821893](http://support.microsoft.com/kb/821893 "The system clock may run fast when you use the ACPI power management timer as a high-resolution counter on Windows 2000-based computers [Q821893]") [MS KB835730](http://support.microsoft.com/kb/835730 "Sound may play slowly or music may not play continuously in Windows XP or Windows 2000 [Q835730]") [MS KB895980](http://support.microsoft.com/kb/895980 "Programs that use the QueryPerformanceCounter() function may perform poorly in x64-based versions of Windows [Q895980]") [MS KB896256](http://support.microsoft.com/kb/896256 "Computers that are running Windows XP Service Pack 2 and that are equipped with multiple processors that support processor power management features may experience decreased performance [Q896256]") [MS KB909944](http://support.microsoft.com/kb/909944 "Game performance may be poor on a Windows XP-based computer that is using a dual-core processor [Q909944]")
 
 The [WinXP MSCONFIG](/article/win2k-msconfig.html) makes it easy to configure the BOOT.INI, and it works with Win2k.  
  
 More info [MS KB99743](http://support.microsoft.com/kb/99743 "Purpose of the BOOT.INI File (Q99743) [Q99743]")  
 More info [MS KB102873](http://support.microsoft.com/kb/102873 "BOOT.INI and ARC Path Naming Conventions and Usage (MS KB102873) [Q102873]")  
 More info [MS KB170756](http://support.microsoft.com/kb/170756 "Available Switch Options for Windows NT Boot.ini File (MS KB170756) [Q170756]")  
 More info [MS KB160899](http://support.microsoft.com/kb/160899 "How to Hide Boot.ini Entries from Displaying After Multiple Installations [Q160899]")  
 More info [MS KB239780](http://support.microsoft.com/kb/239780 "Safe-Mode Boot Switches for Windows Boot.ini File [Q239780]")  
 More info [MS KB289022](http://support.microsoft.com/kb/289022 "HOW TO: Edit the Boot.ini File in Windows XP (MS KB289022) [Q289022]")  
 More info [MS KB311578](http://support.microsoft.com/kb/311578 "HOW TO: Edit the Boot.ini File in Windows 2000 [Q311578]")  
 More info [MS KB314081](http://support.microsoft.com/kb/314081 "The Purpose of the Boot.ini File in Windows XP [Q314081]")  
 More info [MS KB317526](http://support.microsoft.com/kb/317526 "HOW TO: Edit the Boot.ini File in Windows Server 2003 [Q317526]")  
 More info [MS KB323427](http://support.microsoft.com/kb/323427 "HOW TO: Manually Edit the Boot.ini File in a Windows Server 2003 Environment [Q323427]")  
 More info [MS KB833721](http://support.microsoft.com/kb/833721 "Available switch options for the Windows XP and the Windows Server 2003 Boot.ini files [Q833721]")  
 More info [MS KB833722](http://support.microsoft.com/kb/833722 "Available switch options for the Windows 2000 Boot.ini file [Q833722]")  
 More Info [MSDN - Boot.ini Boot Parameter Reference](http://msdn2.microsoft.com/en-gb/library/ms791480.aspx)  
  
 Credits [SysInternals.com](http://www.sysinternals.com/)