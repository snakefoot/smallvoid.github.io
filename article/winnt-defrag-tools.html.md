---
title: 'Defragmentation utilities to remove file fragmentation'
date: '2000-01-01T19:42:36+01:00'
status: publish
permalink: /article/winnt-defrag-tools.html
author: Snakefoot
excerpt: 'Different utilities available to keep file fragmentation at a low level, and maintain good hard disk performance.'
type: post
id: 367
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - defrag
    - disk-performance
    - file-system
    - hard-disk-drive
    - ntfs
post_format: []
tags:
    - 'defrag,ntfs,hard-disk-drive,disk-performance'
---
The Windows NT Filesystem (NTFS) generates less [file fragmentation](/article/defrag-hard-disk-partition.html) compared to FAT16/FAT32. File fragmentation still occurs, but one doesn't have to defrag so often.  
  
 Windows NT provides an API that 3rd party defragmentation tools can use defragment partitions. The initial API for online defragmentation was rather limited, but have been extended with each new versions of Windows NT.

- Cannot defragment NTFS partitions with a [cluster size](/article/cluster-hard-disk-partition.html) larger than 4 KByte (Increased to 64 KByte with WinXP)
- Cannot defragment NTFS system files like [MFT](/article/winnt-ntfs-mft.html). (Limitation removed with WinXP)
- Cannot defragment directories (Limitation removed with Win2k)
- Cannot move a single cluster at a time but 16 at a time (Limitation removed with WinXP)
- More Info [MS KB227463](http://support.microsoft.com/kb/227463 "Disk Defragmenter Limitations in Windows 2000, Windows XP, and Windows Server 2003 [Q227463]"), [MS KB942092](http://support.microsoft.com/kb/942092 "Features of the Windows Vista hard disk defragmentation utility")
 
 To get around these limitation the 3rd party tools has to perform an offline/boot-time defragmentation. Windows 2000/XP includes a lite edition of Execsoft DisKeeper, which can perform an online defragmentation.  
  
 The following 3rd party freeware defragmenting tools are available:
- [SysInternals PageDefrag](http://www.microsoft.com/technet/sysinternals/utilities/pagedefrag.mspx "SysInternals Pagefrag") (Offline defragmentation only)
- [Execsoft DiskKeeper Lite](http://www.execsoft.com/downloads/menu.asp "Execsoft DiskKeeper Lite") [Download DisKeeper](http://www1.execsoft.com/dklite.exe "Execsoft DisKeeper Lite 7.0 Build 418") (Has nag screen)
- [O&amp;O Defrag 2000](http://www.oo-software.com/en/products/ood2000free/index.html) [Mirror](http://www.majorgeeks.com/O&O_Defrag_2000_Freeware_Edition_d4545.html)
- [Kessels JkDefrag](http://www.kessels.com/JkDefrag/) (Open Source)
- [DIRMS &amp; BUZZSAW](http://www.dirms.com/ "Do It Right MicroSoft") (Command-line)
- [UltraDefrag - Ultra Defragmenter](http://ultradefrag.sourceforge.net/ "Dmitri Arkhangelski") (Opensource)
- [IObit SmartDefrag](http://www.iobit.com/iobitsmartdefrag.html)
- [Piriform Defraggler](http://www.defraggler.com/)
- [Auslogics Disk Defrag](http://www.auslogics.com/en/software/disk-defrag)
- Command line wrappers for dfrg.msc in Windows 2000 (XP has [defrag.exe](/article/winnt-defrag-switches.html)): 
  - [AutoDefrag](http://sourceforge.net/projects/autodefrag/)
  - [StartDefrag](http://kevin.gearhart.com/startdefrag/)
 
 There also exists tools that one can pay money for:
- [Execsoft DiskKeeper Full version](http://www.diskeeper.com/)
- [Raxco PerfectDisk](http://www.raxco.com/products/perfectdisk2k/)
- [O&amp;O Defrag](http://www.oo-software.com/)
- Norton Speeddisk for NT by [Symantec](http://symantec.com/)
- [Vopt](http://www.vopt.com/)
- [Paragon - Total Defrag](http://www.paragon-software.com/home/total-defrag/)
 
 Related [Compress Old Files causes defrag to hang in Win2k/WinXP](/article/cleanup-profiles.html)  
  
 Credits [ArsTechnica.com](http://www.arstechnica.com/)