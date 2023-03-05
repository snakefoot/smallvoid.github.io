---
title: 'Use NTFS compression to save disk space'
date: '2008-06-14T16:59:43+02:00'
status: publish
permalink: /article/winnt-ntfs-compress.html
author: Snakefoot
excerpt: 'NTFS compression can compress / decompress files on the fly and save disk space and minimize needed hard disk I/O'
type: post
id: 767
category:
    - Tips
    - Tips
tag:
    - file-system
    - free-disk-space
    - ntfs
post_format: []
tags:
    - 'ntfs,free-disk-space'
---
The Windows NT filesystem (NTFS) supports compression, which mean that one can mark a single file or a folder of files to be compressed. When NTFS compresses a file, then it chops the file up in small fragments and compresses each fragment.

- NTFS compression supports quick random access, because it can easily look up the right fragment.
- NTFS compression can slow down streaming access to files if CPU power is limited, but else NTFS can increase disk performance because decompression is often faster than the hard disk.
- NTFS compression can fail if the file is very large (beyond 100 MByte), because the it has to split the file into many fragments.
- NTFS compression should not be used on files that are already in compressed state like archives-files (ZIP, RAR, etc.) and media-files (MP3, AVI, etc.).
 
 Windows 2000 extended the [Cleanup Wizard](/article/cleanup-profiles.html) to automatically compress non-critical files, that aren't accessed frequently. Over time this should lower the disk space required by the Windows installation. If disk space is critical on the install partition, then one can trim the installation size by activating NTFS compression manually.  
  
 Folders on Windows XP:
- **C:\\Windows\\Installer** - Contains all the uninstallers for the programs installed on the computer. If deleting the contents of this folder then it will be very difficult to uninstall any program currently installed.
- **C:\\Windows\\Installer\\$PatchCache$** - When applying updates then the original files are stored in this folder. If deleting the contents of this folder then it will not be possible to uninstall patches or updates for any program currently installed.
- **C:\\Windows\\ServicePackFiles** - Used by [Windows File Protection](/article/winnt-wfp.html) to make sure that when installing new components then the latest install files are used. Can avoid the directory if installing Windows with the latest service pack [slipstreamed](/article/winxp-install-slipstream.html).
- **C:\\Windows\\$hf\_mig$** - Used by Windows Installer to ensure that when installing new Windows Updates, then it will keep the latest version of the install files in case two updates tries to update the same file.
- **C:\\Windows\\$NtServicePackUninstall$** - Allows Windows to uninstall a service pack without needing the original install CD. If not planning to remove an installed service pack, then one can remove the uninstall option and save disk space.
- **C:\\Windows\\SoftwareDistribution\\Download** - Used by Automatic Updates to store downloaded updates for Windows. You can clear this directory (with subdirectories) if Windows Update is not running.
- Other things to consider for freeing disk space:
  - Limit the space for System Restore Points
  - [Clean Temporary Directories](/article/cleanup-profiles.html)
  - Limit the space for [Temporary Internet Files](/article/ie-temporary-internet-files.html)
  - [Disable Hibernate File](/article/winnt-hibernation.html)
  - Uninstall unnecessary [Windows Components](/article/winnt-add-remove-all.html)
 
 Folders on Windows Vista: - None
- Other things to consider for freeing disk space:
  - Windows Vista SP1 File Removal Tool - Vsp1cln.exe (Is included with Vista SP1)
  - Windows Vista SP2 File Removal Tool - Compcln.exe (Is included with Vista SP2)
  - Remove media sample files (music and movies) installed by default with Vista. Open Media Player and browse the Library of Music and Movies to delete them.
  - The Windows Side By Side folder (WinSxS) should not be touched, as it is a solution to [DLL Hell](http://en.wikipedia.org/wiki/DLL_hell) by giving the ability of having the same DLL in multiple versions. The folder is completely system managed, and the size of the folder is a bit misleading as it contains NTFS hard links to files in other directories. Windows will regularly purge the directory for obsolete files/links, so the size of the folder will grow and shrink dynamically.