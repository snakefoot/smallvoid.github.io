---
title: 'Encrypted backup to OneDrive or DropBox'
date: '2016-08-07T22:09:08+02:00'
status: publish
permalink: /article/encrypted-backup-cloud.html
author: Snakefoot
excerpt: 'Create removable encrypted hard-disk-image, and use that for Windows Backup.'
type: post
id: 5291
category:
    - Tips
tag:
    - backup
    - bitlocker
    - encryption
    - file-system
    - hard-disk-drive
post_format: []
---
When making a backup and giving it to stranger, then it is good idea to encrypt the backup.  
  
 Many file cloud services gives one a folder or a drive, where one can place the files for backup. This provides no protection besides the empty promises of the so called stranger.  
  
 One solution to this problem is to create an encrypted disk-image, and then place the backup on this disk-image. Then one can just place disk-image-file where the file-cloud-service can find it.

##### How to create to an encrypted disk-image

1. Open "Disk Management"
2. Open menu "Action" and select "Create VHD"
3. Choose **VHD** with a **Fixed size** of your choice 
  - Notice that OneDrive have file-size limit of 10 GByte, so the disk-image cannot be larger than that.
4. The newly created disk needs to be initialized, so right-click the disk and choose "Initialized". Choose **MBR** partition style.
5. The newly initialized disk needs a partition, so right-click the disk and choose "New Simple Volume". Format the disk as **NTFS** with allocation unit size of **64K**
6. The newly created partition will now be visible as a drive on the computer. Right-click the drive and choose "Turn on BitLocker". Use the BitLocker Compatibility Mode for easier access.

##### How to mount the disk-image

 After reboot/restart then the disk-image will not be loaded by default.
1. Open "Disk Management"
2. Open menu "Action" and select "Attach VHD"

##### How to make a backup to the disk-image

1. Open the Windows Backup
2. Choose the newly encrypted drive as the backup location
3. Choose the folders you want to backup
4. Start the backup
 
 One have to detach/unmount the disk-image before the cloud-file-service can upload the file. This is also done in "Disk Management".  
  
##### Schedule weekly/monthly script with these operations:

1. Mounts the disk-image, and waits for BitLocker password to be entered.
2. Triggers Windows Backup to make incremental backup

- Maybe every half-year then performs full-backup and removes old incremental backups