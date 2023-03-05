---
title: 'Apply the DirextX runtime installer after updating drivers'
date: '2000-01-01T02:03:21+01:00'
status: publish
permalink: /article/windows-update-directx.html
author: Snakefoot
excerpt: 'Update the DirectX runtime after installing new drivers to prevent conflicts.'
type: post
id: 232
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - directx
post_format: []
tags:
    - directx
---
After installing new drivers for your graphics adapter or soundcard always remember to install the [newest DirectX](http://www.microsoft.com/downloads/results.aspx?freetext=DirectX%20Redist&sortCriteria=date), even if you have the newest DirectX version installed already. This will make DirectX adapt to the new drivers.  
  
 It is also a good idea to re-configure the Sound Acceleration after messing with sound- or directx-drivers:

1. Open **Control Panel** and select the sound configuration applet: 
  - Sounds (Win95/Me).
  - Sounds and Multimedia (WinMe/Win2k).
  - Sounds and Audio Devices (WinXP).
2. Select the **Audio**-tab and press **Advanced**-button for **Sound Playback** and the window **Advanced Audio Properties** comes up.
3. Select the **Speakers**-tab and select your speaker setup (If already selected, then change it, press **Apply** and then change it back).
4. Select the **Performance**-tab and slide the **Hardware Acceleration** to **Full** (If already Full, then slide it down, press **Apply** and then change it back).
5. Press **Ok**-button to accept the new audio configuration.
 
 It is also a good idea to re-configure the Graphics Acceleration after messing with display- or directx-drivers:
1. Open **Control Panel** and select the **Display properties**-applet.
2. Select the **Settings**-tab and press the **Advanced...**-button.
3. Select the **Troubleshooting**-tab and set **Hardware Acceleration** to **Full** (If already Full, then slide it down, press **Apply** and then change it back).
4. One might also check the display configuration tabs provided by the manufacture (Those tabs usually has icons).
5. Press **Ok**-button to accept the new graphics configuration.
 
 Another good idea after installing Sound-, Graphics- or DirectX-Drivers is to run DirectX Diagnostics (DxDiag.exe). It can discover many configurations errors with a few simple tests. If it complains about not being able to use hardware buffering in the sound test then go through the above steps to enable sound acceleration (or reinstall soundcard drivers).