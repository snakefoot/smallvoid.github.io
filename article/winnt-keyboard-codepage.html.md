---
title: 'Change keyboard codepage'
date: '2002-03-14T04:09:23+01:00'
status: publish
permalink: /article/winnt-keyboard-codepage.html
author: Snakefoot
excerpt: 'How to change the codepage for the command prompt.'
type: post
id: 22
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - codepage
    - keyboard
post_format: []
tags:
    - 'keyboard,codepage'
---
If you have problems using the keyboard in programs run from the command line (cmd.exe), then you might need to change your codepage, so it fits with your national settings.  
  
 This is can be done with this STRING value in the registry:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Nls \\Codepage\]  
>  OEMCP = "850" (Default = 437)

 One can also change the codepage from the command prompt (Will only have effect for the current session):
 > mode con cp select=850

 To see current codepage from the command prompt:
 > mode con

 <table border="1"><tr><th align="center">Country</th><th align="center">Codepage</th></tr><tr><td>United States, UK</td><td align="center">437</td></tr><tr><td>Multilingual</td> <td align="center">850</td></tr><tr><td>Slavic</td> <td align="center">852</td></tr><tr><td>Portuguese</td> <td align="center">860</td></tr><tr><td>Icelandic</td> <td align="center">861</td></tr><tr><td>Canadian, French</td> <td align="center">863</td></tr><tr><td>Scandinavian/Nordic</td><td align="center">865</td></tr></table>

 Note it is possible for an application to change the codepage by using the [setLocale](http://msdn.microsoft.com/library/en-us/vccore98/HTML/_crt_setlocale.2c_._wsetlocale.asp) function. There is also [SetConsoleCP](http://msdn.microsoft.com/library/en-us/dllproc/base/setconsolecp.asp?frame=true) / [SetConsoleOutputCP](http://msdn.microsoft.com/library/en-us/dllproc/base/setconsoleoutputcp.asp), but they don't work with the default raster font, but requires that the console is using a truetype font like Lucida Console. More Info [MS KB99795](http://support.microsoft.com/kb/99795 "INFO: SetConsoleOutputCP Only Effective with Unicode Fonts [Q99795]").  
  
 More Info [MS KB314010](http://support.microsoft.com/kb/314010 "DCA Fails When OEMCP Is Set to a Value Other Than 437 (United States) [Q314010]")