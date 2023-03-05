---
title: 'Change the display of share comment in My Network Places'
date: '2006-03-16T21:50:13+01:00'
status: publish
permalink: /article/winnt-share-comment.html
author: Snakefoot
excerpt: 'Control in what order the share name and share comment should be shown in My Network Places.'
type: post
id: 415
category:
    - Desktop
tag:
    - network-places
    - visual-style
post_format: []
tags:
    - 'network-places,visual-style'
---
Windows XP displays by default shares from other computers the following way:

> *share\_name on comment\_text (computer\_name)*

 It is possible to change the position of computer\_name, so it is shown next to share\_name:
 > *share\_name on computer\_name (comment\_text)*

 This is done with this registry key:
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer\]  
>  ToggleCommentPosition = 1 (0 = Default)  
>   
>  More Info [MS KB330193](http://support.microsoft.com/kb/330193 "The computer description appears before the computer name in Windows XP [Q330193]")