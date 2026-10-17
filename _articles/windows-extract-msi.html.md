---
title: 'Extract files from a MSI package'
date: '2006-01-18T00:06:34+01:00'
permalink: /article/windows-extract-msi.html
author: Snakefoot
excerpt: 'The Microsoft Installer (MSI) Package file is a compressed archive, which can be decompressed.'
type: post
id: 289
categories:
    - windows-2003_tips
    - windows-95_tips
    - windows-98_tips
    - windows-me_tips
    - windows-nt4_tips
    - windows-xp_tips
    - windows-2000_tips
tags:
    - command-line-switches
    - microsoft-installer-package
---
Usually it is possible to use ones favorite compression utility to treat a Microsoft Installer Package (MSI) like it was a normal archive. Though sometimes it doesn't work, but then one can use the Windows Installer Tool (Msiexec.exe) to extract the files from the MSI package. It can open a MSI package in "Administrator" installation mode, where it can extract the files without performing the install.  
  
 Runs setup where one can select where to extract the files without actually installing the application:

> Msiexec /a mypackage.msi

 Extracts the files to the specified location without user interaction:
 > msiexec /a mypackage.msi /qb TARGETDIR="C:\\MyFolder"

 Note this can also be useful in case an MSI package has been configured to block install, when used on certain versions of Microsoft Windows.  
  
 More Info <a href="https://www.bing.com/search?q=KB+227091+Q227091" rel="nofollow" title="Command-Line Switches for the Microsoft Windows Installer Tool [Q227091]">MS KB227091</a>  