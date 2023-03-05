---
title: 'DOS emulation in Windows NT'
date: '2001-05-16T14:38:41+02:00'
status: publish
permalink: /article/winnt-dos-emulator.html
author: Snakefoot
excerpt: 'DOS box extensions for Windows NT to play the old DOS games one love so dearly.'
type: post
id: 494
category:
    - Utilities
    - Utilities
    - Utilities
    - Utilities
tag:
    - dos-emulator
    - dos-subsystem
post_format: []
tags:
    - 'dos-emulator,dos-subsystem'
---
Windows NT includes a [MS-DOS subsystem](/article/winnt-autoexec-config.html) to execute 16 bit programs (and games). This subsystem is rather limited in functionality and compatibility, so if one tries to execute a DOS program in Windows NT then it will most likely fail.

- Windows XP adds Sound Blaster 2.0 support in the Virtual DOS Machine (NTVDM), so if missing sound in a DOS game, then configure the DOS game to use Sound Blaster 2.0 (Port: 220, IRQ: 5, DMA Channel: 1) and General MIDI (Port: 330) for music. This can also be seen if looking in the [autoexec.nt](/article/winnt-autoexec-config.html):
> SET BLASTER=A220 I5 D1 P330 T3
 
[DOSBox](http://dosbox.sourceforge.net/) is probably the most advanced and complete DOS emulator available. It is mainly developed for games, and tries to emulate the entire x86 hardware, so it can be quite slow on low-end hardware.  
  
 Extensions for the existing MS-DOS subsystems: - [VDMSound](http://sourceforge.net/projects/vdmsound/) - Soundcard emulator for Windows NT4/2000 dos boxes.
- [SoundFX 2000](http://www.softsystem.co.uk/page4.htm) - Uses directsound to emulate any soundcard as a soundblaster 16 in Windows NT4/2000/XP dos boxes.
- [dgVoodoo](http://www.freeweb.hu/dege/) - Is a glide wrapper that uses directdraw to implement the Glide interface created by 3DFX, so one can play in Glide-mode even if not having a 3DFX Voodoo card.