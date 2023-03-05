---
title: 'Slipstream Service pack before installing Windows 2000'
date: '2001-01-01T04:39:25+01:00'
status: publish
permalink: /article/win2k-install-slipstream.html
author: Snakefoot
excerpt: 'Apply the service pack before making the install for a faster and more secure install.'
type: post
id: 479
category:
    - 'Install CD'
tag:
    - free-disk-space
    - slipstream
    - windows-install
post_format: []
tags:
    - 'slipstream,windows-install,free-disk-space'
---
Microsoft created this new feature with Windows 2000, allowing you to update the install files with the files from a service pack. This enables you to apply a service pack before actually making the install.  
  
 Slipstreaming will save HDD space as the C:\\WINNT\\ServicePackFiles isn't needed. This folder is created when you install a service pack, so you don't have to reinstall the service pack when you install new components. The folder easily takes about 200 MByte.

1. Copy the contents of your Win2k CD-ROM to a new folder **c:\\win2kcd**
2. Download the [Network Installation](http://www.microsoft.com/windows2000/downloads/servicepacks/default.asp) of the wanted service pack
3. Create a new folder **c:\\win2ksp**
4. Run the service pack .exe file with the parameter -x and when it asks where to extract point to **c:\\win2ksp**
  - One can also open the service pack .exe file with WinZip and extract the files to **c:\\win2ksp**
5. Go to the **c:\\win2ksp\\i386\\update** folder and run (If getting :
   > UPDATE.EXE -S:c:\\win2kcd
6. Check that the following files exists in the root of **c:\\win2kcd**
  - cdrom\_i?.5 
      - cd-rom\_ip.5, If Professional Edition
      - cd-rom\_is.5, If Server Edition
      - cd-rom\_ia.5, If Advanced Server Edition
      - cd-rom\_id.5, If Datacenter
  - cdrom\_nt.5
  - cdromsp?.tst 
      - cdrom\_sp.tst, If Service Pack 1
      - cdromsp2.tst, If Service Pack 2
      - cdromsp3.tst, If Service Pack 3
      - cdromsp4.tst, If Service Pack 4
  - read1st.txt
  - readme.doc
  - setup.exe
  - spnotes.htm
7. Create a bootable CD from the new image 
  - [Create Win2k bootable CD using CDRWIN](/article/win2k-bootable-cd-cdrwin.html)
  - [Create Win2k bootable CD using NERO v5.5.9.0](/article/win2k-bootable-cd-nero.html)
  - [Create Win2k bootable CD using Adaptec EZ CD Creator v5.02d](/article/win2k-bootable-cd-adaptec.html)
 
 Related [nlite - The ultimate deployment tool](/article/winnt-nlite.html)  
 Related [Unattended Windows Guide](http://unattended.msfn.org/)  