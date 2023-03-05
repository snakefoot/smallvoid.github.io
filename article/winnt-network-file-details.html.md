---
title: 'Configure the request of extended file details when opening a file'
date: '2003-10-14T22:11:05+02:00'
status: publish
permalink: /article/winnt-network-file-details.html
author: Snakefoot
excerpt: 'Windows Explorer will automatically request extended file information when trying to open a file on a network share.'
type: post
id: 444
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - network-performance
    - network-share
post_format: []
tags:
    - 'network-share,network-performance'
---
When opening a file over a network, then besides requesting the file contents, then it also request extended details about the file and the share it resides upon. This gives extra traffic and can increase the time it takes to open a file (Especially if on slow network connections like VPN over DialUp).  
  
 One can disable this fetching of extended details by adding the following values to the registry:

> REGEDIT4  
>   
>  \[HKEY\_CLASSES\_ROOT\\\*\\shellex\\PropertySheetHandlers\\{3EA48300-8CF6-101B-84FB-666CCB9BCD32}\]  
>  "SuppressionPolicy"=dword:00100000  
>   
>  \[HKEY\_CLASSES\_ROOT\\\*\\shellex\\PropertySheetHandlers\\{883373C3-BF89-11D1-BE35-080036B11A03}\]  
>  "SuppressionPolicy"=dword:00100000  
>   
>  \[HKEY\_CLASSES\_ROOT\\\*\\shellex\\PropertySheetHandlers\\CryptoSignMenu\]  
>  "SuppressionPolicy"=dword:00100000  
>   
>  \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SCAPI\]  
>  "Flags"=dword:00100c02

 Note the latest service pack for Win2k(SP4) / WinXP(SP1) has to be applied first before it will recognize these registry entries.  
  
 More Info [MS KB321126](http://support.microsoft.com/kb/321126 "The "Look In" and "Save As" Boxes in Common Dialog Boxes Are Slow [Q321126]")  
 More Info [MS KB829700](http://support.microsoft.com/kb/829700 "Slow Network Performance When You Open a File That Is Located in a Shared Folder on a Remote Network Computer [Q829700]")  
  
 Credits [www.jsifaq.com](http://www.jsifaq.com/)