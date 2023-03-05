---
title: 'Create your own sleep / wait program'
date: '2001-01-01T10:56:11+01:00'
status: publish
permalink: /article/sleep-command.html
author: Snakefoot
excerpt: 'How to create your own sleep / wait command, which be used in other batch files.'
type: post
id: 66
category:
    - Tips
tag:
    - batch-file
    - choice
    - ping
    - sleep
post_format: []
tags:
    - 'sleep,batch-file,choice,ping'
---
It can be useful in [batch files](/article/batch-file.html) to have the ability to perform a wait operation for a certain time period. Ex. if polling for a certain event (like a file being created by another program), or if having to perform an action with a certain period of time in between. There is no sleep or wait operation available in DOS, but you can create your own version.  
  
[CHOICE](/article/choice-user-input.html) can be used where one specifies that it should pick the default after a certain period of time. Create a batch file WAIT.BAT with the following lines:

> @REM The &gt; NUL make sure that the screen output from choice is not shown  
>  @CHOICE /T:N,%1% &gt; NUL

 If not having CHOICE available, but have TCPIP PING then one can use this instead:
> @REM The &gt; NUL make sure that the screen output from choice is not shown  
>  @PING 1.0.0.0 -n %1 -w 10 &gt; NUL

 To use WAIT.BAT, call it like this:
> CALL WAIT 10