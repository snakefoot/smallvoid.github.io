---
title: 'Include 3rd party controller drivers using unattended install'
date: '2002-06-01T05:46:03+02:00'
status: publish
permalink: /article/winnt-install-cd-drivers.html
author: Snakefoot
excerpt: 'Avoid having to use a floppy disk when installing Windows NT on a machine with unsupported disk controller.'
type: post
id: 484
category:
    - 'Install CD'
    - 'Install CD'
    - 'Install CD'
    - 'Install CD'
tag:
    - slipstream
    - unattended-install
    - windows-install
post_format: []
tags:
    - 'slipstream,windows-install,unattended-install'
---
When installing Windows NT on a drive connected to a 3rd party controller, which Windows NT doesn't recognize, then one have to press F6 and supply drivers on a floppy unless wanting a [BSOD with INACCESSIBLE\_BOOT\_DEVICE](/article/winnt-inaccessible-boot-device.html).  
  
 The easy way of creating a custom install cd with 3rd party drivers is to use the utility [NLite](/article/winnt-nlite.html) (Requires .NET to use)  
  
 One can manually slipstream the driver on the installation cd, so Windows NT will automatically recognize the controller without having to press F6 and use a floppy disk:

1. Create a directory $OEM$ under the i368 directory:
   > &lt;Drive&gt;\\i386\\$OEM$
2. Create a directory Textmode under the $OEM$ directory:
   > &lt;Drive&gt;\\i386\\$OEM$\\Textmode
3. Copy only the needed drivers for the specific operating system to the Textmode directory. All the files should be placed in the Textmode directory, there should not be created any sub directories below the Textmode directory.  
  > Txtsetup.oem (Required)  
  >  Driver.sys  
  >  Driver.inf  
  >  Driver.cat
4. Edit the file &lt;Drive&gt;\\i386\\$OEM$\\Textmode\\TXTSETUP.OEM and find the \[disks\] section. Ex.:
  > \[disks\]  
  >  d1 = "Windows 2000 Driver Set v1.00", \\w2kdsk1, \\win2000\\ultra160\\
  
   Update the path (\\win2000\\ultra160) so it points to current directory (&lt;Drive&gt;\\i386\\$OEM$\\Textmode) instead of referencing floppy drives or sub directories.  
    
   If installing on a FAT / FAT32 partition then replace the path with period "."
  > \[disks\]  
  >  d1 = "Windows 2000 Driver Set v1.00", \\w2kdsk1, .
  
   If installing on a NTFS partition then replace the path with slash "\\"
  > \[disks\]  
  >  d1 = "Windows 2000 Driver Set v1.00", \\w2kdsk1, \\
  
   All references to other Operating Systems inside the TXTSETUP.OEM should be removed. Example of an [Original](/tweak/winnt/files/txtsetup.oem.before.txt) and [Modified](/tweak/winnt/files/txtsetup.oem.after.txt) image of the TXTSETUP.OEM for a Promise Fasttrak to install on NTFS in WinXP. Credits [spc.org.nc](http://www.spc.org.nc/it/TechHead/index.html)
5. Edit the file &lt;Drive&gt;\\i386\\Unattend.txt, and create a \[MassStorageDrivers\] section:
  > \[MassStorageDrivers\]  
  >  "string that identifies the controller in the \[scsi\] section of TXTSETUP.OEM" = "OEM".
  
   Ex. :
  > \[MassStorageDrivers\]  
  >  "Adaptec Ultra160 Family PCI SCSI Controller (29160, 39160, etc.)" = "OEM"
6. If intending to use the onboard IDE controller during installation, Edit the file &lt;Drive&gt;\\i386\\Unattend.txt, and add this line to the \[MassStorageDrivers\] section:
   > "IDE CD-ROM (ATAPI 1.2)/PCI IDE Controller" = "RETAIL"
  
   If the line is not added a BSOD will appear during install with INACCESSIBLE\_BOOT\_DEVICE. This error comes because the controller which the device(HDD/CD-ROM/DVD) is attached to is not recognized. Therefore requiring one to give it a driver for the controller.Ex. :
  > \[MassStorageDrivers\]  
  >  "Adaptec Ultra160 Family PCI SCSI Controller (29160, 39160, etc.)" = "OEM"  
  >  "IDE CD-ROM (ATAPI 1.2)/PCI IDE Controller" = "RETAIL"
7. Edit the file &lt;Drive&gt;\\i386\\Unattend.txt, and create a \[OEMBootFiles\] section. List the driver filenames copied to the Textmode folder:
  > \[OEMBootFiles\]  
  >  Driver.sys  
  >  Driver.inf  
  >  Driver.cat  
  >  Txtsetup.oem
8. Edit the file &lt;Drive&gt;\\i386\\Unattend.txt, and set the following option in the \[Unattended\] section:
  > \[Unattended\]  
  >  OemPreinstall=Yes  
  >  OemSkipEula=Yes
9. Launch the installation with the created unattend file:
  > WINNT /U:&lt;Drive&gt;\\i386\\Unattend.txt /S:&lt;Drive&gt;\\i386
  
   Note if doing the install from DOS then load [SMARTDRV](/article/hdd-disk-cache-smartdrv.html) before launching the install, or else the initial file copying in textmode will be extremely slow.
 
 Note one can rename the Unattend.txt as Winnt.sif and place it in the i386 directory, and it will use make the unattended install automatically. Another way is to place the Winnt.sif on a floppy disk and insert it before starting the install from the Install-CD.  
  
 Related [Unattended Windows Guide](http://unattended.msfn.org/)  
  
 More Info [MS KB288344](http://support.microsoft.com/kb/288344 "HOWTO: Unattended Installation of Third Party Mass Storage Drivers in Windows NT and Windows 2000 (MS KB288344) [Q288344]")  
 More Info [MS KB155197](http://support.microsoft.com/kb/155197 "HOWTO: Unattended Setup Parameters for Unattend.txt File (MS KB155197) [Q155197]")  
 More Info [MS KB166028](http://support.microsoft.com/kb/166028 "INFO: Installing Third-Party Video Drivers with Txtsetup.oem Unattended (MS KB166028) [Q166028]")  
 More Info [MS KB254078](http://support.microsoft.com/kb/254078 "How to Add OEM Plug and Play Drivers to Windows Installations (MS KB254078) [Q254078]")  
 More Info [MS KB255771](http://support.microsoft.com/kb/255771 "How to Minimize the Installed "Footprint" of Windows 2000 Professional [Q255771]")  
 More Info [MS KB314479](http://support.microsoft.com/kb/314479 "How to Add OEM Plug and Play Drivers to Windows XP [Q314479]")  
 More Info [MS KB816299](http://support.microsoft.com/kb/816299 "HOW TO: Create an Unattended Installation of Third-Party Mass Storage Drivers in Windows Server 2003")  
  
 Credits [jsifaq.com](http://jsifaq.com/)