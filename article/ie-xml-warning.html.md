---
title: 'Disable restriction warning when viewing XML files'
date: '2006-10-12T01:11:21+02:00'
status: publish
permalink: /article/ie-xml-warning.html
author: Snakefoot
excerpt: 'Internet Explorer is restricted to not run scripts when viewing local webpages.'
type: post
id: 324
category:
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
    - 'Internet Explorer (IE8)'
tag:
    - security-zone
    - trusted-sites
post_format: []
tags:
    - 'security-zone,trusted-sites'
---
Internet Explorer 6 in Windows XP SP2 includes extra security, which blocks javascript and vbscript in web-pages placed on the local drive. This security is also activated when opening a XML file placed on the local drive:

> *To help protect your security, Internet Explorer has restricted this file from showing active content that could access your computer. Click here for options...  
>   
>  To help protect your security, Internet Explorer has restricted this webpage from running scripts or ActiveX controls that could access your computer. Click here for options...*

 One cannot browse the XML document without right-clicking the warning and selecting "Allow Blocked Content". This can be quite annoying when daily working with XML files.  
  
 There are two known solutions to this problem:
- Use a different browser/viewer to browse XML documents
- Disable the extra security and allow scripting for all web-pages placed on the local drive 
  1. In Internet Explorer go to the **Tools**-menu and select **Internet Options...**
  2. Go to the **Advanced**-tab and scroll down to **Security** and enable **Allow active content to run in files on My Computer**
   
   This change is reflected in this DWORD registry key:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Internet Explorer \\Main \\FeatureControl\]  
  >  FEATURE\_LOCALMACHINE\_LOCKDOWN = 0
 
 More info [MS KB878461](http://support.microsoft.com/kb/878461 "Pictures do not appear as expected, or you receive an error message when you open an HTML file on a Windows XP Service Pack 2-based computer [Q878461]")  
 More info [MS KB883969](http://support.microsoft.com/kb/883969 "AutoShapes that were added to an HTML or an MHTML file in a Microsoft Office program do not appear when you open the file in Internet Explorer after you install Windows XP SP2 [Q883969]")  
 More info [MS KB910878](http://support.microsoft.com/kb/910878 "You receive a security warning when you open a FrontPage 2003 Web page that uses JavaScript in Internet Explorer [Q910878]")  
  
 Credits [phdcc.com](http://www.phdcc.com/xpsp2.htm)