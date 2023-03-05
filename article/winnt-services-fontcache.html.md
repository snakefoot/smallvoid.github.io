---
title: 'Windows Presentation Foundation Font Cache'
date: '2007-07-17T02:18:16+02:00'
status: publish
permalink: /article/winnt-services-fontcache.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Presentation Foundation Font Cache service.'
type: post
id: 726
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - font
    - WPF
post_format: []
tags:
    - 'WPF,font'
---
##### Description:

 Optimizes performance of Windows Presentation Foundation (WPF) applications by caching commonly used font data. WPF applications will start this service if it is not already running. It can be disabled, though doing so will degrade the performance of .NET 3.0 WPF applications.  
  
 More Info [Wiki - Windows Presentation Foundation (WPF)](http://en.wikipedia.org/wiki/Windows_Presentation_Foundation)  
 More Info [MSDN - Windows Presentation Foundation (WPF)](http://msdn.microsoft.com/en-us/library/ms754130.aspx)  
 More Info [MS KB937135](http://support.microsoft.com/kb/937135 "Error message when you run a Windows Presentation Foundation (WPF)-based application in the .NET Framework 3.0
")  
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (FontCache)
- WinXP/Vista - PresentationFontCache.exe (FontCache)

##### Supports:

- none

##### Depends:

- none