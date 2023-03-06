---
title: 'Configure the page file for best performance'
date: '2000-01-01T02:14:32+01:00'
status: publish
permalink: /article/windows-page-file.html
author: Snakefoot
excerpt: 'Finding the the optimal size and location for the Windows swap file.'
type: post
id: 233
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - free-disk-space
    - page-file
    - swap-file
    - virtual-memory
post_format: []
tags:
    - 'swap-file,page-file,virtual-memory,free-disk-space'
---
When using Windows NT operating systems, then the best configuration for the pagefile is to let Windows handle it by setting it to be system managed. So unless having a very special system configuration, then one should just leave the pagefile alone.  
  
 When using Windows 9x operating system, then one can consider to set a custom size for the page file. The system managed page file in Win9x is constantly resized depending on the memory load, which increases [file fragmentation](/article/defrag-hard-disk-partition.html).

##### Why using a page file?

 In the early days RAM was very limited, and it created limitations on how large applications could be. Large applications could get around this limitation by dividing themselves into small modules, and then manually load the needed modules from disk into RAM, and unload the vacant modules from RAM. It created the illusion of having more RAM than actually available. There was also some operating systems, which used swapping to unload/load entire applications in and out of RAM, thus giving the illusion of being able to have several applications running even though the RAM was limited. The above methods were somewhat cumbersome to implement especially as applications became larger and more complex. Virtual memory became a solution to these problems.
 
##### How does virtual memory and the page file work?

 The operating system splits all the available memory (Whether it is RAM or disk) into small memory pages (Usually 4 KByte) and controls the access to these pages. The applications uses the operating system to access the memory-pages, and the operating system is responsible for loading/unloading of memory pages without exposing this to the applications. The unloading/loading is controlled by a paging algorithm, which keeps the most frequent used memory-pages in RAM and unloads the less frequent memory-pages to the disk. When an application requests an unloaded memory page, then a [page fault](/article/windows-pagefault.html) is created, and the application is blocked until the memory page is loaded from the disk and back into RAM.
 
##### Why is the performance of the page file not important?

 Unloading memory-pages from the RAM to the page file on the disk is a very slow operation. The disk is at least a thousand times slower than RAM (nanosec vs, milisec and GByte/sec vs. Mbyte/sec), so at all times one should make sure to always have enough RAM. No matter what pagefile configuration is used, it will always lead to a grinding halt if the system have used up all the RAM. Therefore the best pagefile configuration is the one which gives the least [file fragmentation](/article/defrag-hard-disk-partition.html) and doesn't take up too much space. <a name="BEST_SIZE"></a>
 
##### How to calculate the necessary page file size?

 Windows will by default configure the pagefile size to be 1.5 times the total RAM (With a maximum of 3 times of total RAM), and this will satisfy most computer configurations. The default configuration of 1.5 times the total RAM comes from the Windows Server environment, where the page file is used for complete memory dump analysis. More Info [MS KB254649](http://support.microsoft.com/kb/254649 "Overview of memory dump file options for Windows Server 2003, Windows XP, and Windows 2000") [MS KB237740](http://support.microsoft.com/kb/237740 "How to overcome the 4,095 MB paging file size limit in Windows")  
  
 The term "commit charge" specifies how much memory the system is using a the moment. If the commit charge is higher than the available RAM, then the system performance will be low (Recommended to have enough RAM to handle peak commit charge). If the commit charge comes close to the total amount of memory available (RAM + pagefile) then applications will start crashing, and Windows might crash as well.  
- To monitor the commit charge use the Task Manager (CTRL+SHIFT+ESC) and go to the Performance-tab. The **Commit Charge (K) Peak** shows the maximum memory usage since system start, and usually one should have more RAM installed than this number. There are also some pretty graphs that will show the current commit charge: 
  - Windows XP/2003 - "PF Usage" and "Page File Usage History".
  - Windows 2000/NT4 - "MEM Usage" and "Memory Usage History".
  - Windows Vista - Doesn't show any graph and the commit charge value have been renamed to "Page File - Value1 / Value2", where Value1 is the commit charge and Value2 is the actual pagefile size.
 
 Unless doing full memory dump analysis, then the pagefile should only work as a buffer in the situation where the commit charge becomes higher than the available RAM. There is no golden rule for how to calculate the size of the pagefile, but here is one from Microsoft:
1. Set your pagefile to be system managed
2. Use your computer like you normally do by running your favorite applications and games
3. After using the computer a few hours then check the page file peak usage. [WinXP-2K\_Pagefile.zip](http://billsway.com/notes_public/WinXP_Tweaks) contains a VB Script that can display the current size of the pagefile, but also the peak size. 
  - Minimum page file should be 1.7 times the page file peak size.
  - Maximum page file should be twice the minimum page file size.
 
 More Info [MS KB889654](http://support.microsoft.com/kb/889654/ "How to determine the appropriate page file size for 64-bit versions of Windows Server 2003 or Windows XP")  
 More Info [MS Technet - Understanding Memory Usage in Windows 2000](http://technet.microsoft.com/en-us/library/bb742598.aspx)  
##### Where to place the page file ?

- **Pagefile type**: 
  - **Dynamic**, where the pagefile grows depending on memory load: 
      - Minimum size is 0 and maximum size must satisfy the extreme memory load.
      - Will only take disk space when needed.
      - The resizing will increase file fragmentation, thus overall disk access will become slower over time.
      - The max memory load is dependent on disk space available.
  - **Permanent**, where the pagefile max. and min. size is the same: 
      - Minimum size and maximum size is the same and must satisfy the extreme memory load.
      - Will have to take a lot more disk space than there is needed.
      - The permanent size will avoid file fragmentation.
      - The max memory load is dependent on the permanent size.
  - **Semi-permanent**, where the pagefile has an initial permanent size but can grow if needed: 
      - Minimum size satisfies the common memory load and maximum size must satisfy the extreme memory load.
      - Will take a little more disk space than there is usual needed, by its initial size.
      - Only when the memory load peaks, then it will cause file fragmentation.
      - The max memory load is dependent on disk space available.
- **Pagefile disk**: 
  - **Primary-disk**, where the pagefile is placed on the same disk as the operating system: 
      - Will share the disk with the other applications (Like the operating system).
  - **Separate-disk**, where the pagefile is placed on its own disk: 
      - The operating system and the pagefile should always be placed on the fastest disk, so unless the separate-disk has the same speed as the primary-disk, then the it will not be the optimal setup.
      - Will have the disk for itself, at least until other files are placed on the disk, so make sure to only use it for storage (Movies/Music/etc.).
      - If the separate disk only contains the pagefile, then one can increase the performance by [enabling write-caching for the hard disk](/article/hard-disk-cache.html).
      - Note that if it is an [IDE HDD system](/article/troubleshoot-hdd-dma.html), and the separate-disk is placed as slave on the same IDE-cable as the primary-disk, then it will slowdown the disk-access for both disks.
  - **Multiple-disks**, where the pagefile is spanned over several partitions on different disks: 
      - Like with the separate-disk, the pagefile should only be placed on the fastest disk(s).
      - Will divide the pagefile load to several disks.
      - The internal algorithm that decides which pagefile to use, will choose the pagefile on the disk that less frequently used. Ensure that the disks used for pagefiles are not heavily accessed.
  - **RAM-disk**, where the pagefile is placed in the physical memory: 
      - Requires that one have enough RAM to satisfy twice the common memory load.
      - Will lower the limit for when the paging algorithm will start paging to free up memory for file caching.
      - The paging algorithm will spend unnecessary time on moving data from one part of the RAM to the other, when reaching the limit on the available physical memory.
  - **RAID-disks**, where the pagefile is placed on a partition spanned over several disks: 
      - RAID-0 gives best performance when doing sequential read/write, this doesn't help the pagefile as it is accessed randomly thus dependent on HDD seek time
      - RAID-1 gives best performance when doing sequential read and gives fault tolerance, this doesn't help the pagefile as it is accessed randomly thus dependent on HDD seek time, and the fault tolerance introduces a write overhead.
- **Pagefile partition**: 
  - **Primary-Partition**, the first partition on the disk: 
      - Normally the fastest partition, as it is placed on the outer tracks on the disk.
      - A dynamic pagefile will cause fragmentation.
      - A permanent pagefile will always occupy more space than needed. This means that the fastest location on the HDD is wasted, instead of being used for files that are frequently paged into memory like DLL- and EXE-files.
      - To lower HDD seek time to the files frequently paged into memory (Operating System, Applications, Pagefile), then the primary partition should be sized to fit these files so they are grouped together. Storage files (Music/Movies/etc.) should be placed on a separate partition as they are not very dependent on HDD seek times.
  - **Dedicated-Partition**, where the pagefile is placed on its own partition: 
      - Normally slower than the primary partition, as it is placed after the primary partition.
      - Will still share the disk with the other applications, when they access files on the other partitions. (Like the operating system).
      - A dynamic or semi-permanent pagefile will get the advantages/disadvantages of a permanent pagefile: 
            - The pagefile will not become fragmented.
            - Will take more disk space than there is normally needed.

##### What is the best pagefile configuration?

 Most people will get the best configuration by using a **Semi-Permanent**-pagefile, which is placed on the C-Drive along with the operating system (**Primary-Partition** on the **Primary-Disk**). The minimum size of the pagefile should support the usual maximum memory load of when running your favorites applications and/or games. This is the default configuration of the Windows NT operating systems, and one should keep the page file set to "System Managed Size".  
- If having another physical hard disk available besides the primary hard-disk and it is just as fast, then one can consider to split the pagefile over both hard-disks. One should ensure that the extra hard disk is not frequently accessed by other applications.
 
 Note the partition used for the pagefile should be formatted with a [cluster](/article/cluster-hard-disk-partition.html)-size, which is equal or larger than the size of a memory page (Usually 4 KByte). If smaller then it is required to access several clusters when reading/writing a memory page.  
  
 Note the access to the pagefile is mostly random and not sequential, so fragmentation in the pagefile doesn't matter much, unless the pagefile have been completed shattered in small fragments over the entire disk. If still wanting to make continuous pagefile, then disable the pagefile or move the pagefile to another partition, and defragment the intended partition before creating the pagefile. Another solution is the utility [PageDefrag](http://technet.microsoft.com/en-us/sysinternals/bb897426.aspx)  
  
 Note WinNT+ will not be able to create a proper memory dump for debugging purpose if the pagefile is disabled or too small. The pagefile is accessed with low level file operations to avoid the NTFS overhead. This allows use of the pagefile to save the dump even if the rest of the subsystems have crashed. Therefore if the pagefile is too small, then it cannot be used to contain the dump.  
  
 More Info [MS KB197379](http://support.microsoft.com/kb/197379 "Configuring page files for optimization and recovery in Windows Server 2003, in Windows 2000, and in Windows NT [Q197379]")  
 More Info [MS KB314482](http://support.microsoft.com/kb/314482 "How to configure paging files for optimization and recovery in Windows XP [Q314482]")  
##### How to configure the page file properties in Windows

 To setup pagefile in Win9x [MS KB259184](http://support.microsoft.com/kb/259184 "How to Increase the Memory Capability of Your Computer [Q259184]"):
1. Start Button -&gt; Settings -&gt; Control Panel -&gt; System -&gt; Performance tab -&gt; Virtual Memory.
2. Select "Let me specify my own virtual memory settings".
3. Set minimum and maximum size.
 
 To setup pagefile in WinNT [MS KB123747](http://support.microsoft.com/kb/123747 "Moving the Windows Default Paging and Spool File [Q123747]"):
1. Start Button -&gt; Settings -&gt; Control Panel -&gt; System -&gt; Performance tab.
2. Under "Virtual Memory" press the "Change..." button.
3. Check "Let me specify my own Virtual Memory Settings".
4. Set initial and maximum size.
 
 To setup pagefile in Win2k [MS KB123747](http://support.microsoft.com/kb/123747 "Moving the Windows Default Paging and Spool File [Q123747]"):
1. Start Button -&gt; Settings -&gt; Control Panel -&gt; System -&gt; Advanced tab.
2. Under "Performance" press "Performance Options..." button.
3. Under "Virtual Memory" press "Change..." button.
4. Set initial and maximum size.
 
 To setup pagefile in WinXP [MS KB307886](http://support.microsoft.com/kb/307886 "HOW TO: Move the Paging File in Windows XP [Q307886]"):
1. Start Button -&gt; Control Panel -&gt; Performance and Maintenance -&gt; System -&gt; Advanced tab.
2. Under the "Performance" section press "Settings" button.
3. Under the "Virtual Memory" section press the "Change..." button.
4. Set initial and maximum size (or just select "System Managed Size").
 
 To setup pagefile in Vista [WindowsHelp](http://windowshelp.microsoft.com/Windows/en-US/help/596fb57f-cc9d-4ac5-a813-5c0830e9156a1033.mspx "Get maximum performance from Windows Vista"):
1. Start Button -&gt; Control Panel -&gt; System-applet -&gt; Advanced System Setting-task -&gt; Advanced-tab -&gt; Performance Settings...-button -&gt; Advanced-tab -&gt; Virtual Memory Change...-button (phew).
2. Untick "Automatically manage paging file size for all drives"
3. Set initial and maximum size (or just tick "Automatically manage paging file size for all drives" back again, and leave it be).
 
 Note in WinNT+ there is an option to [Clear the Windows Paging File at Shutdown (MS KB182086)](http://support.microsoft.com/kb/182086 "How to Clear the Windows Paging File at Shutdown [Q182086]") and it is not recommended for the home user. It will increase the time it takes to shutdown because it has to write zero's in the whole pagefile on the HDD. The reason for enabling clearing is to avoid that a very skilled person can open the pagefile and spy on the things you were doing while logged in (It requires that the person has physical access to the machine).  
  
 More Info [MS KB175639](http://support.microsoft.com/kb/175639 "Windows 95/98 and Windows NT 4.0 Can Share Virtual Memory [Q175639]")  
 More Info [MS KB837869](http://support.microsoft.com/kb/837869 "Error message when you when you start or play a Microsoft game: "Your system is low on virtual memory" [Q837869]")  
 More Info [MS KB889654](http://support.microsoft.com/kb/889654 "How to determine the appropriate page file size for 64-bit versions of Windows Server 2003 or Windows XP [Q889654]")  
  
 Related [Disable the page file to avoid using the slow HDD](/article/windows-disable-page-file.html)  
 Related [Make sure your IDE HDD is performing at its best](/article/troubleshoot-hdd-dma.html)  
  
 Credits [RojakPot.com](http://www.rojakpot.com/)