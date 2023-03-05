---
title: 'Extract files from a MSI package'
date: '2006-01-18T00:06:34+01:00'
status: publish
permalink: /article/windows-extract-msi.html
author: Snakefoot
excerpt: 'The Microsoft Installer (MSI) Package file is a compressed archive, which can be decompressed.'
type: post
id: 289
category:
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
    - Tips
tag:
    - command-line-switches
    - microsoft-installer-package
post_format: []
tags:
    - 'microsoft-installer-package,command-line-switches'
---
Usually it is possible to use ones favorite compression utility to treat a Microsoft Installer Package (MSI) like it was a normal archive. Though sometimes it doesn't work, but then one can use the Windows Installer Tool (Msiexec.exe) to extract the files from the MSI package. It can open a MSI package in "Administrator" installation mode, where it can extract the files without performing the install.  
  
 Runs setup where one can select where to extract the files without actually installing the application:

> Msiexec /a mypackage.msi

 Extracts the files to the specified location without user interaction:
 > msiexec /a mypackage.msi /qb TARGETDIR="C:\\MyFolder"

 Note this can also be useful in case an MSI package has been configured to block install, when used on certain versions of Microsoft Windows.  
  
 More Info [MS KB227091](http://support.microsoft.com/kb/227091 "Command-Line Switches for the Microsoft Windows Installer Tool [Q227091]")  