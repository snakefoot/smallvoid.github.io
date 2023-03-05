---
title: 'Change OEM branding of the Welcome Center'
date: '2008-10-02T02:43:02+02:00'
status: publish
permalink: /article/winnt-oem-welcome-center.html
author: Snakefoot
excerpt: 'The Welcome Center applet can be modified to display OEM name and logo.'
type: post
id: 771
category:
    - Desktop
tag:
    - branding
    - oem
    - welcome-center
post_format: []
tags:
    - 'branding,oem,welcome-center'
---
The Welcome Center is the Control Panel applet launched when starting Windows Vista for the first time. It contains links to different topics about the features available in Windows Vista.

![](/tweak/winnt/pictures/vista-welcome-center.jpg)

 It is possible for an OEM system builder to customize the Welcome Center, so it also includes special links to products and features added by the OEM system builder. More Info [Walkthrough: Customize Welcome Center](http://technet.microsoft.com/en-us/library/cc749597.aspx).  
  
 If wanting to modify the Welcome Center after Windows Vista has been installed, then it can be done by editing **Oobe.xml**. The **&lt;useroobe&gt;** xml-node contains the Welcome Center modifications.  
  
 The location of the **Oobe.xml** can be one of the following places:
- %WINDIR%\\System32\\Oobe\\Info\\Oobe.xml
- %WINDIR%\\System32\\Oobe\\Info\\Default\\&lt;language&gt;\\Oobe.xml
- %WINDIR%\\System32\\Oobe\\Info\\&lt;country&gt;\\&lt;language&gt;\\Oobe.xml
 
 More Info [Oobe.xml Settings](http://technet.microsoft.com/en-us/library/cc722154.aspx)  
  
 Credits [Unlock for Us](http://unlockforus.blogspot.com/2008/01/branding-your-windows-vista-computer.html "Branding your Windows Vista Computer")