---
title: 'Configuring environment variables in Windows NT'
date: '2003-02-28T20:28:53+01:00'
status: publish
permalink: /article/winnt-environment-variables.html
author: Snakefoot
excerpt: 'Description of the different types of environment variables in the Windows NT system.'
type: post
id: 269
category:
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
    - 'Command Prompt'
tag:
    - environment-variables
post_format: []
tags:
    - environment-variables
---
Environment variables are used almost everywhere in Windows, and there are several types of environment variables: (Listed in initialization order)

1. System generated like %DATE%, %TIME%, %SYSTEMROOT%, %COMPUTERNAME%, created when Windows starts
2. Local Machine specified (Same for all users ex. [PATH](/article/executing-program-path.html))
3. [AUTOEXEX.BAT](http://support.microsoft.com/kb/124551 "INFO: Configuring Parsing of the AUTOEXEC.BAT File [Q124551]") specified
4. System generated like %USERNAME%, %USERDOMAIN% and %USERPROFILE% are created when user logs in
5. User specified (Unique for this user)
6. [Command Prompt specified](/article/environment-variables.html) (Lives and dies with the command prompt)
 
 Local Machine and User specified variables can be configured here:
 - WinNT4 : Control Panel -&gt; System -&gt; Environment-tab
 - Win2k/Xp : Control Panel -&gt; System -&gt; Advanced-tab -&gt; Environment Variables-button
 
 They can also be accessed through the registry (STRINGs) :
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\Session Manager \\Environment\]  
>   
> \[HKEY\_CURRENT\_USER \\Environment\]

 Note the environment variables will be available both in the Cmd.exe and the MS-DOS Environment Command.com.  