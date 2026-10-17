---
title: 'Change keyboard codepage'
date: '2002-03-14T04:09:23+01:00'
permalink: /article/winnt-keyboard-codepage.html
author: Snakefoot
excerpt: 'How to change the codepage for the command prompt.'
type: post
id: 22
categories:
    - windows-nt4_command-prompt
    - windows-xp_command-prompt
    - windows-2000_command-prompt
    - windows-2003_command-prompt
tags:
    - codepage
    - keyboard
---
If you have problems using the keyboard in programs run from the command line (cmd.exe), then you might need to change your codepage, so it fits with your national settings.  
  
 This is can be done with this STRING value in the registry:

> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Nls \\Codepage\]  
>  OEMCP = "850" (Default = 437)

 One can also change the codepage from the command prompt (Will only have effect for the current session):
 > mode con cp select=850

 To see current codepage from the command prompt:
 > mode con

 <table border="1">
 <tr><th align="center">Country</th><th align="center">Codepage</th></tr>
 <tr><td>United States, UK</td><td align="center">437</td></tr>
 <tr><td>Multilingual</td> <td align="center">850</td></tr>
 <tr><td>Slavic</td> <td align="center">852</td></tr>
 <tr><td>Portuguese</td> <td align="center">860</td></tr>
 <tr><td>Icelandic</td> <td align="center">861</td></tr>
 <tr><td>Canadian, French</td> <td align="center">863</td></tr>
 <tr><td>Scandinavian/Nordic</td><td align="center">865</td></tr>
 </table>

 Note it is possible for an application to change the codepage by using the [setLocale](http://msdn.microsoft.com/library/en-us/vccore98/HTML/_crt_setlocale.2c_._wsetlocale.asp) function. There is also [SetConsoleCP](http://msdn.microsoft.com/library/en-us/dllproc/base/setconsolecp.asp?frame=true) / [SetConsoleOutputCP](http://msdn.microsoft.com/library/en-us/dllproc/base/setconsoleoutputcp.asp), but they don't work with the default raster font, but requires that the console is using a truetype font like Lucida Console. More Info <a href="https://www.bing.com/search?q=KB%2099795%20Q99795" rel="nofollow" title="INFO: SetConsoleOutputCP Only Effective with Unicode Fonts [Q99795]">MS KB99795</a>.  
  
 More Info <a href="https://www.bing.com/search?q=KB%20314010%20Q314010" rel="nofollow" title="DCA Fails When OEMCP Is Set to a Value Other Than 437 (United States) [Q314010]">MS KB314010</a>