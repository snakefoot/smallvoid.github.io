---
title: 'Checkpoints for fixing a bad or corrupt BIOS flash'
date: '2002-08-14T22:20:53+02:00'
status: publish
permalink: /article/flash-motherboard-bios.html
author: Snakefoot
excerpt: 'Description of different alternative ways for recovering from a bad BIOS flash.'
type: post
id: 272
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - BIOS
    - motherboard
    - system-recovery
post_format: []
tags:
    - 'motherboard,bios,system-recovery'
---
Before going down this road, then please make sure that the BIOS hasn't stopped working because of a [bad cmos or hardware conflict](/article/repair-motherboard-bios.html).

- Contact [bad flash](http://www.badflash.com/) and have them send you a new BIOS.
- If your motherboard is supporting dual BIOS, then one have a backup BIOS which one can switch to. This is the case with [Gigabyte DualBIOS](http://www.giga-byte.com/home/dualb.htm) [Aopen DieHard BIOS](http://www.aopen.com/tech/techinside/diehard.htm) [MSI Safe BIOS](http://www.msi.com.tw/). For more information look in your motherboard manual.
- If your motherboard BIOS is supporting boot block, then it will allow you to boot from a floppy disk and reflash. Though in early versions it only supports ISA VGA cards (Meaning no display for PCI/AGP VGA cards). 
  - How to use boot block on Award BIOS 
      1. Create a standard bootable floppy disk
      2. Add a good(older) BIOS image file along with flash utility
      3. If in the "No Display" scenario then create an AUTOEXEC.BAT which executes a command line BIOS flasher to the BIOS, Ex.:
         > awdflash.exe a7v1005c.awd /py /sn
      4. Attach only the following devices : CPU, RAM, Keyboard(Not USB), Floppy (No HDD, CD-ROM, Sound, Modem, NIC what so ever)
      5. Insert the created floppy disk and boot the machine and pray that it starts reading from your floppy drive
      6. It should then make some beep codes 
            - 2 short beeps = no bootable diskette in drive A
            - continual short beeps = no floppy disk drive
            - continual long beeps = programming finishes, reset your system
  - How to use boot block on AMI BIOS 
      1. Format a floppy disk
      2. Copy a good(older) BIOS image file to the floppy disk
      3. Rename the BIOS image file on the floppy disk so the filename becomes "AMIBOOT.ROM"
      4. Start the machine with the floppy disk in drive
      5. Hold down the keyboard keys CTRL+Home to force the update
      6. After some minutes the system will beep 4 times meaning the flashing is complete
- Use the risky Hot Flash, if you know someone with a similar motherboard as you : 
  1. Let him boot from a floppy with flash utilities and BIOS image like he was going to flash his own motherboard
  2. Take the BIOS chip out of your motherboard
  3. Exchange it with the one in his motherboard while his machine is running
  4. Reflash your BIOS chip in his motherboard using the flash utilities on the floppy
  5. Shutdown his machine put the BIOS chips back
 
 More Info [UniFlash.org](http://www.uniflash.org/)