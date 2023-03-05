---
title: 'Setup switches for Windows 9x installation'
date: '2002-05-27T00:21:30+02:00'
status: publish
permalink: /article/win9x-setup-switches.html
author: Snakefoot
excerpt: 'Useful command line switches that can be used when installing Windows 95 / 98 / Me.'
type: post
id: 173
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - command-line-switches
post_format: []
tags:
    - command-line-switches
---
Some of the more exciting command line switches:

- **/NTLDR**  disables detection of existing Windows (Allows to install Windows Retail on top of an existing install)
- **/nm**  allows to install Windows ignoring hardware demand (Ex. 486).
- **/im**  allows to install Windows ignoring memory demand.
- **/p** If needing several /p options then separate them with semicolon ex. setup /p j;g=3 
  - **/p f** only works with Windows 95 (Not 98, Me). It makes it possible to repair, by reinstalling on top of the existing one, as it forces it to redetect all hardware again. (One have to run the setup from MS-DOS)
  - **/p i** forces Windows NOT to use ACPI/PnP (Useful if having an older PnP BIOS not supported by Windows and have trouble installing or running Windows)
  - **/p j** forces Windows to use ACPI/PnP (Useful if having a newer ACPI BIOS not recognized by Windows 98 Machines.inf)
  - **/p g=3**  makes the setup give more verbose debug information. Good when having problems with installing and one need to identify the problem area.
 
 More Info [MS KB128400](http://support.microsoft.com/kb/128400 "Windows 95 Setup Switches [Q128400]")  
 More Info [MS KB186111](http://support.microsoft.com/kb/186111 "Description of the Windows 95, Windows 98, and Windows Me Setup Switches [Q186111]")  