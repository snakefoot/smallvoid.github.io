---
title: 'Checkpoints for fixing no BIOS POST'
date: '2002-08-14T22:20:52+02:00'
status: publish
permalink: /article/repair-motherboard-bios.html
author: Snakefoot
excerpt: 'Steps for fixing a computer which cannot perform BIOS POST.'
type: post
id: 271
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
If the computer BIOS (Basic Input Output System) cannot perform POST (Power On Self Test):

- Check CPU Fan and that is attached to the power outlet for CPU fan and that it spins when power is turned on (Some motherboards cannot POST if CPU fan fails to report active).
- Clear the motherboard [CMOS](http://www.computeruser.com/resources/dictionary/popup_definition.php?lookup=1446), by looking in the motherboard manual for how to do (Usually removing the battery for 15 minutes will solve the issue)
- If using jumpers to overclock your machine (Voltage and Multipliers) then put the machine back to default setting or jumperless
- If nothing fixed, then make sure the PC Speaker is attached properly and listen if any [beep-codes](http://bioscentral.com/beepcodes/awardbeep.htm) and if so consult your motherboard manual for the meaning
- Try to warm boot the machine, this is done by turning on power (cold boot) and let everything spin up and then press reset-button (Warm Boot). If this fixes the problem then the power supply doesn't supply enough power.
- Clear the cabinet from dust, as it might cause short circuit.
- Take out and reinsert all devices like PCI, AGP and memory modules in case of bad connection.
- If still no beep codes, then one have cut down the problem area
- Pull out all unnecessary PCI cards, leaving only the Display Adapter
- Pull out all but one memory module (Make sure that the one is working)
- Pull the power from all HDD, CD-ROMs, DVDs.
- Reboot and see if problem is fixed, and if so plug each pulled out device back in one by one.
- If nothing fixed, pull out the Display Adapter and the memory module.
- Reboot and see if it gives beep codes, if so consult your manual for their meaning (It might be caused by faulty memory slot or incompatible memory module)
- If no beep codes when only having the CPU attached, then pull out the CPU.
- Reboot and see if it gives beep codes, if so then something might be wrong with the CPU or the CPU temperature
- If no beep codes with a clean motherboard, then try another power supply (Which is known to work)
- If no beep codes then try to remove the motherboard from the case and check that no metal objects like a screw or bare wire is short circuiting.
- If still no beep codes then there is the following possibilities 
  - Using a lousy PC Speaker
  - Using a lousy Power Supply
  - [A bad or corrupt BIOS flash](/article/flash-motherboard-bios.html)
  - The motherboard is dead, return it to the shop