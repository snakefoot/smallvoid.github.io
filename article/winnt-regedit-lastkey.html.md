---
title: 'Stop Regedit from remembering previous location'
date: '2001-11-03T20:55:32+01:00'
status: publish
permalink: /article/winnt-regedit-lastkey.html
author: Snakefoot
excerpt: 'Configure whether the registry editor should show the last registry location when started.'
type: post
id: 390
category:
    - Tips
    - Tips
    - Tips
tag:
    - regedit
post_format: []
tags:
    - regedit
---
When starting regedit then it go to the registry-location, which it displayed last time before it was closed.  
  
 This behavior can be disabled with the following steps:

1. Run Regedt32 (Not regedit) which enables you to set security for registry keys
2. Go to this location:
   > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Applets \\Regedit\]
3. Find the entry "LastKey"
4. Select the entry and from the menu select Security / Permissions
5. Deny Full Control to the currently logged in user
 
 More Info [MS KB244004](http://support.microsoft.com/kb/244004 "HOW TO: Prevent Regedit.exe from Using the Last State [Q244004]")  
  
 Related [Let regedit remember your registry favorites](/article/windows-registry-favorites.html)  
  
 Credits [ntcanuck.com/tq](http://ntcanuck.com/tq/)  