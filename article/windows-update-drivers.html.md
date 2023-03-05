---
title: 'Update hardware drivers and firmware to improve stability'
date: '2000-01-01T00:45:47+01:00'
status: publish
permalink: /article/windows-update-drivers.html
author: Snakefoot
excerpt: 'Description of how the drivers and firmware for the computer hardware should be updated to get the best performance.'
type: post
id: 229
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - BIOS
    - chipset
    - dialup-modem
    - drivers
    - firmware
    - hardware
    - motherboard
post_format: []
tags:
    - 'hardware,firmware,motherboard,drivers,dialup-modem,chipset,bios'
---
When hardware is released then it usually contains a lot of undiscovered bugs. These bugs are many times severe and causes crashes/slowdowns/malfunction at special circumstances. Over time these bugs are discovered and are usually solved with driver or firmware updates released by the manufactures.  
 To make sure the computer is stable and performing at its best, then it is a good idea to keep an eye out for driver and firmware updates made for your system.  
  
 The first thing to find out is what hardware, that resides inside the computer. This is usually provided in the manuals, which came with the computer, but if this is not the case then one can one of these programs to help out:

- [SiSoftware Sandra Standard](http://www.sisoftware.net/index.html?dir=dload&location=sware_dl_x86)
- [PC Wizard](http://www.cpuid.com/pcwizard.php)
- [WinAudit](http://www.pxserver.com/WinAudit.htm)
- [Lavalys EVEREST Home Edition](http://www.majorgeeks.com/download4181.html)
 
 The next thing is to check whether updated drivers/firmware exists for the hardware, where the following parts are especially important to check out:
 - **Motherboard Chipset Drivers**:  
   The default drivers in Windows seldom take advantage of all the features on your motherboard. This can result in instability and low graphics(AGP)- and memory-performance. There are several chipset manufactures: [Intel](http://support.intel.com/), [AMD](http://www.amd.com/us-en/Processors/TechnicalResources/0,,30_182_871,00.html), [Via Hyperion 4in1](http://www.viaarena.com/), [Nvidia Unified Driver](http://www.nvidia.com/content/drivers/drivers.asp), Ali, [SIS](http://www.sis.com/download/)  
   Note sometimes some motherboards are created as combination of two different chipsets (Ex. AMD+VIA), and one is required to install chipsets drivers for both of them. It can be a good idea to visit the motherboard manufacture homepage (Asus, MSI, Abit, Epox, etc.) and see if they have created a driver package.
- **Motherboard BIOS**:  
   After a motherboard has been released several errors and lack of features are discovered. The motherboard manufacture usually create new BIOS revisions to take care of many of the discovered bugs. By updating/flashing your motherboard with a newer BIOS revision then there is a good chance you improve stability.
- **IDE/SCSI controller drivers and firmware**:  
   The default drivers in Windows might lead to a very slow performance when accessing HDD and CD-ROM drives (Or not give any access at all). By updating the Controller drivers higher disk performance is usually gained.  
    
   Note the onboard IDE-Controller drivers are usually supplied with the Motherboard Chipset Drivers from the motherboard manufacture.
- **Display Adapter drivers and firmware**:  
   The default drivers in Windows seldom take advantage of the features your graphics adapter has. By updating the drivers with the one from the graphics chipset manufacture (Nvidia, Ati, Matrox, S3), then one can access to higher resolutions and higher performance in D3D and OpenGL.
- **Soundcard drivers**:  
   The default drivers in Windows will usually allow one to play sounds and hear music. But if using the soundcard for playing games, then it is important to update the drivers as it will usually improve hardware acceleration(avoid stuttering and delay) and give features like 3D Sound.
- **Network Interface Card (NIC) drivers**:  
   The default drivers in Windows will most likely be quite sufficient. Though if wanting to activate special features like onboard processor or network priority, then it is probably best to use the drivers from the NIC manufacture.
- **Modem firmware and drivers**:  
   By using updated firmware and drivers there is a chance of turning an old 33.6 modem into a 56.6 modem or higher depending on the modem manufacture.