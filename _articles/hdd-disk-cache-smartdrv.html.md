---
title: 'Increase HDD speed with disk cache'
date: '2000-01-01T15:45:44+01:00'
permalink: /article/hdd-disk-cache-smartdrv.html
author: Snakefoot
excerpt: 'Description of how a disk cache will help HDD performance, and how to activate the smart drive disk cache.'
type: post
id: 44
categories:
    - ms-dos_performance
tags:
    - autoexec-bat
    - disk-performance
    - file-cache
    - file-system
    - smartdrv
---
Smart Drive (SMARTDRV) is a disk cache driver, which creates a disk cache in the extended memory. When a program requests data from the HDD or CDROM the data is also copied to the disk cache, so if the program asks for the data again then it will not require to access the slow HDD or CDROM. When a program reads a file then it usually process it in small chunks. While the program is processing a single chunk, then the disk cache is able to read-ahead several small chunks of the file and have them ready in memory.  
  
 Edit AUTOEXEC.BAT and update/insert this line:

> C:\\Dos\\Smartdrv.exe 2048

 Note if loading MSCDEX.EXE for CD-ROM support, then load SMARTDRV after MSCDEX.EXE so the CD-Drives also gets a diskcache.  
  
 Note smart drive can also be loaded into the [Upper Memory Block](/article/load-drivers-high-memory.html) to free conventional memory.  
  
 More Info <a href="https://www.bing.com/search?q=KB%2081377%20Q81377" rel="nofollow" title="SMARTDrive /double_buffer Cannot Load into UMBs [Q81377]">MS KB81377</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2081607%20Q81607" rel="nofollow" title="Rebooting from a Batch File with SMARTDRV.EXE Loaded [Q81607]">MS KB81607</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2082709%20Q82709" rel="nofollow" title="SMARTDRV Cache Status -- What Does the Buffering Value Mean? [Q82709]">MS KB82709</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2083376%20Q83376" rel="nofollow" title="SMARTDrive ElementSize Should Precede CacheSizes [Q83376]">MS KB83376</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2084706%20Q84706" rel="nofollow" title="Troubleshooting SMARTDrive Version 4.0 [Q84706]">MS KB84706</a>  
 More Info <a href="https://www.bing.com/search?q=KB%2095531%20Q95531" rel="nofollow" title="SMARTDrive: Maximum Cache Size [Q95531]">MS KB95531</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20241458%20Q241458" rel="nofollow" title="HOWTO: Speed the Preinstallation Process for Windows 9x [Q241458]">MS KB241458</a>  