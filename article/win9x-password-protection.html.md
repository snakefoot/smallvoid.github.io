---
title: 'Bypassing user password protection in Windows 9x'
date: '2000-01-01T00:57:17+01:00'
status: publish
permalink: /article/win9x-password-protection.html
author: Snakefoot
excerpt: 'Getting past the password protection in Windows 9x.'
type: post
id: 177
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - password
    - windows-login
post_format: []
tags:
    - 'windows-login,password'
---
The password protection in Windows 9x is very low, if not configured correctly.

- If there is a standard local login request then at most times one can just press Esc to get past it, or just login as another user.
- If there is a forced local login then one can just press F8 at startup to enter DOS and remove all .pwl files in the Windows directory.
- If there is a forced network login then one can just press CTRL+ESC, which starts the task manager, from which you can start "explorer".
 
 Related [Bypassing a screen saver with password using autorun](/article/win9x-screensaver-password.html)