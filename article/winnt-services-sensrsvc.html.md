---
title: 'Adaptive Brightness'
date: '2009-09-16T01:13:16+02:00'
status: publish
permalink: /article/winnt-services-sensrsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Adaptive Brightness service.'
type: post
id: 794
category:
    - 'Services Guide'
tag:
    - power-management
post_format: []
tags:
    - power-management
---
##### Description:

 Uses the light sensors on the monitor (if available) to detect changes in ambient light and adjust the display brightness. If this service is stopped or disabled, the display brightness will not adapt to lighting conditions.  
  
 To turn adaptive brightness on or off:
1. Open **Power Options** through **System and Security** in the **Control Panel**
2. Under any plan, click **Change plan settings**.
3. Click **Change advanced power settings**.
4. In the list, expand **Display**, and then expand **Enable adaptive brightness**.
 
 To enable the Ambient Light Sensor (ALS):
1. Open **Location and Other Sensors** through **Hardware and Sound** in the **Control Panel**
2. There the ALS hardware should be listed and can be enabled using the checkbox
 
 More Info [Adjusting brightness automatically using adaptive brightness](http://windows.microsoft.com/en-US/windows7/Adjust-your-monitors-brightness-and-contrast)> Adaptive brightness is not available in all editions of Windows 7.

##### Recommended state:

- Manual

##### Default State:

- Windows 7: Manual

##### Proces name:

- [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (SensrSvc)

##### Supports:

- none

##### Depends:

- none