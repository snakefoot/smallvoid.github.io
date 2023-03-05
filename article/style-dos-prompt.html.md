---
title: 'Change the style of the DOS prompt (C:\)'
date: '2000-01-01T19:20:01+01:00'
status: publish
permalink: /article/style-dos-prompt.html
author: Snakefoot
excerpt: 'Description of the options available for styling the DOS prompt.'
type: post
id: 49
category:
    - Tips
tag:
    - visual-style
post_format: []
tags:
    - visual-style
---
The prompt is usually specified in AUTOEXEC.BAT and the standard prompt "c:\\&gt;" is :

> prompt $p$g

 <table border="0" cellpadding="10"><tr><td> <table border="2" cellpadding="2" cellspacing="1"><tr><th>Command</th> <th>Effect</th></tr><tr><td>$t</td> <td>current time</td></tr><tr><td>$d</td> <td>current date</td></tr><tr><td>$p</td> <td>current path</td></tr><tr><td>$n</td> <td>current driveletter</td></tr><tr><td>$v</td> <td>current version</td></tr><tr><td>$e</td> <td>escape character</td></tr><tr><td>$h</td> <td>backspace character</td></tr><tr><td>$\_</td> <td>newline character</td></tr></table>

</td><td> <table border="2" cellpadding="2" cellspacing="1"><tr><th>Command</th> <th>Effect</th></tr><tr><td>$g</td> <td>&gt;</td></tr><tr><td>$l</td> <td>&lt;</td></tr><tr><td>$q</td> <td>=</td></tr><tr><td>$$</td> <td>$</td></tr><tr><td>$b</td> <td>|</td></tr><tr><td>$a</td> <td>&amp;</td></tr><tr><td>$c</td> <td>(</td></tr><tr><td>$f</td> <td>)</td></tr></table>

</td></tr></table>

 With these characters one can create an individual prompt:
> prompt time is: $t$\_date is: $d$\_path is: $p$g

 If one loads ANSI.SYS in the CONFIG.SYS then the prompt is also capable of changing colors by using escape sequences "$e\[" (Here Bright Red and Green).
> prompt $e\[1;31;40m$p$g$e\[1;32;40m  
>   
>  More Info [MS KB83064](http://support.microsoft.com/kb/83064 "Using ANSI.SYS /X to Remap Extended Keys [Q83064]")  
>  More Info [MS KB135484](http://support.microsoft.com/kb/135484 "Windows 95 CD-ROM Msdosdrv.txt File (1 of 2) [Q135484]") (Escape Sequences &amp; Color Codes etc.)