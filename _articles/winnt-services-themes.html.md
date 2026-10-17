---
title: 'Themes Service'
date: '2003-06-05T19:52:54+02:00'
permalink: /article/winnt-services-themes.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Themes service.'
type: post
id: 608
categories:
    - windows-2003_services
    - windows-xp_services
    - windows-vista_services
    - windows-7-win7_services-guide
tags: []
---
##### Description:

 Provides user experience theme management.  
  
 Related [Using themes for styling the visual appearance](/article/windows-customize-visually.html)  
  
 Note if disabled then it will only be possible to select **Windows Classic**-theme, and the **Windows Classic style**-Windows and buttons.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20307855%20Q307855" rel="nofollow" title="HOW TO: Configure Desktop Themes in Windows XP [Q307855]">MS KB307855</a>  
  
##### Recommended State:

- Automatic, if using themes to skin the user interface.

##### Default State:

- WinXP: Automatic.
- Win2k3: Disabled.
- Vista: Automatic.

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Themes)

##### Supports:

- None

##### Depends:

- None