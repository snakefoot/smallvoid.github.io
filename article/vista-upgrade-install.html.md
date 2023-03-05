---
title: 'Perform clean install using Windows Vista upgrade'
date: '2007-08-28T02:03:05+02:00'
status: publish
permalink: /article/vista-upgrade-install.html
author: Snakefoot
excerpt: 'Installing Windows Vista without needing to install an older version of Windows first.'
type: post
id: 735
category:
    - Troubleshoot
tag:
    - windows-install
post_format: []
tags:
    - windows-install
---
Windows Vista doesn't allow one to use the install cd of a previous version of Windows to authenticate as it being an upgrade of a full version. Instead one has to install the old version of Windows first, and then boot into Windows to install Windows Vista. More Info [MS KB930985](http://support.microsoft.com/kb/930985 "Upgrade installation keys are blocked when you start from the Windows Vista DVD").  
  
 The work-around is to use the upgrade-cd to install a non-activated version of Vista (faster), and then perform an inplace upgrade (cleaner):

1. Boot using the Vista Install DVD.
2. Click **Install Now** and do not enter a **Product Key** when prompted and uncheck **Automatically activate Windows when I'm online**.
3. Pick the proper product edition (Home Basic, Home Premium, Business, or Ultimate) when prompted and install Vista.
4. After the install has completed, then launch the Vista install again, but do it from within the newly installed Windows Vista.
5. Select to perform an **Upgrade** and now enter the **Product Key** when prompted.
 
 Credits [WindowsITPro.com](http://www.windowsitpro.com/)