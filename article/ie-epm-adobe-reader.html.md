---
title: 'Open PDF in Internet Explorer 11 with Adobe Reader'
date: '2014-01-11T14:21:29+01:00'
status: publish
permalink: /article/ie-epm-adobe-reader.html
author: Snakefoot
excerpt: 'How to fix Adobe Reader X so it will work with Internet Explorer 11 (x64) Enhanced Protection Mode'
type: post
id: 839
category:
    - 'Web Browser'
tag:
    - acrobat-reader
    - enhanced-protected-mode
    - ie-plugin
    - pdf
post_format: []
tags:
    - enhanced-protected-mode
---
> **\*Update\* 13 May 2014** Adobe have released Adobe Reader XI ver. 11.0.07 that includes 64 bit plugin, so this workaround is no longer needed.  
>   
>  Remember to activate "Protected Mode" for all files ("Preferences" -&gt; "Security (Enhanced)".

 Internet Explorer 11 Enhanced Protected Mode (64 bit) mode doesn't work well with Adobe Reader. For some reason the Adobe Reader installer performs faulty registration of the PDF file, so it can only be opened if the IE plugin is active.  
  
 IE 11 (64 bit) will not run 32 bit plugins, and so nothing happens when trying to open a PDF file. I guess with some investigation, then one could fix the faulty registration of the PDF file, so it would just open the file normally. But here is another workaround:
1. Install Adobe Reader and upgrade to latest version
2. Make a backup of the Adobe install folder:
  > C:\\Program Files (x86)\\Adobe
3. Uninstall the Adobe Reader
4. Copy the Adobe-folder back to the Program Files (x86)-folder
5. Execute the following registry script (Use 11.0 if Adobe Reader XI):
  > Windows Registry Editor Version 5.00  
  >   
  >  \[HKEY\_CURRENT\_USER\\Software\\Adobe\\Acrobat Reader\\10.0\\AdobeViewer\]  
  >  "TrustedMode"=dword:00000000  
  >  "EULA"=dword:00000001  
  >  "Launched"=dword:00000001
6. Open a PDF document with Adobe Reader (browse to folder) and mark it as default application