---
title: 'Activate Aero Interface on Windows Vista Home Basic'
date: '2007-07-02T07:45:40+02:00'
status: publish
permalink: /article/vista-basic-aero.html
author: Snakefoot
excerpt: 'Bypass the restriction of not being able to use the Aero interface on Windows Vista Home Basic.'
type: post
id: 653
category:
    - Desktop
tag:
    - aero
    - crippled
    - window-transparency
post_format: []
tags:
    - 'aero,crippled,window-transparency'
---
Windows Vista Home Basic has been crippled by Microsoft to not support Aero, but will instead use "Windows Vista Basic" or "Windows Vista Standard" appearance. By changing a few registry settings, then it is possible to configure the Desktop Windows Manager (DWM) to enable the Aero Interface like in Home Premium.

1. Update the following DWORD registry keys to force Aero on Vista Basic:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\DWM\]  
  >  Composition = 1  
  >  CompositionPolicy = 2
2. Restart the computer.
3. Turn on the Aero Interface as one would normally do: 
  1. Right click on the desktop and select "Personalize".
  2. Choose "Window Color and Appearance".
  3. Click the blue link titled "Open classic appearance properties for more color options".
  4. Change the color-scheme from "Windows Vista Basic" to "Windows Aero".
 
 Note in Windows Vista Home Basic the "Window Color and Appearance" window will now include a colour picker along with a slider to change Color intensity. Besides these changes it will be no different than using the "Windows Vista Standard" appearance. The "Enable Transparency" will NOT be there, so there is no [Glass effect](http://www.microsoft.com/technet/abouttn/flash/tips/tips_092805_2.mspx), and it will not enable [Flip 3D](http://www.microsoft.com/windows/products/windowsvista/features/details/flip3D.mspx).  
  
 Note "Windows Aero" and "Windows Vista Standard" is only available when meeting the [minimum hardware requirements](http://technet.microsoft.com/en-us/windowsvista/aa905075.aspx) as specified by the [Vista rules](http://www.microsoft.com/whdc/device/display/aero_rules.mspx "Windows Vista Rules for Enabling Windows Aero"):
- WDDM Display Driver installed
- DirectX 9 compatible
- Pixel Shader 2 capable
- 32 bits per pixel supported
- Minimum 64 MB graphics memory (128 MB if resolution beyond 1280\*960)
- 512 MB system memory if dedicated graphics memory (1 GB RAM if shared graphics memory)
 
 There is reason why Aero is only activated if having the right hardware, as the desktop experience would be too slow. It is possible to disable this machine check and enable Aero no matter what by creating these DWORD keys:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\DWM\]  
>  UseMachineCheck = 0  
>  Blur = 0  
>  Animations = 0

 Note if having modified the hardware or updated the drivers, so the computer meets the requirements to run Aero, then one can activate Aero by running an assessment:
1. Open Control Panel and choose "System And Maintenance"
2. Click "Performance Information And Tools" and click the link "Update my score" (if no existing score "Score this computer")
 
 Credits [Petri.co.il](http://www.petri.co.il/)