---
title: 'Remove the splash screen in Outlook Express / Windows Mail'
date: '2001-04-17T17:55:57+02:00'
status: publish
permalink: /article/outlook-express-splash-screen.html
author: Snakefoot
excerpt: 'The splash screen can be useful to see if an application is actually starting, but it can also be disabled.'
type: post
id: 329
category:
    - 'Outlook Express'
    - 'Windows Mail (Vista)'
tag:
    - splash-screen
post_format: []
tags:
    - splash-screen
---
This is done with this DWORD in the registry:  
  
 For Outlook Express 4.0 :

> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Outlook Express\]  
>  NoSplash=1

 For Outlook Express 5.0 / 6.0 :
> \[HKEY\_CURRENT\_USER \\Identities \\{GUID} \\Software \\Microsoft \\Outlook Express \\5.0\]  
>  NoSplash=1

 For Windows Mail (Vista) :
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows Mail\]  
>  NoSplash=1