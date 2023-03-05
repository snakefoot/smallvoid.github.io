---
title: 'Configure the task grouping in the taskbar'
date: '2003-02-21T21:01:35+01:00'
status: publish
permalink: /article/winnt-taskbar-grouping.html
author: Snakefoot
excerpt: 'Change how multiple instances of the same application should be grouped together.'
type: post
id: 409
category:
    - Desktop
tag:
    - task-grouping
    - taskbar
post_format: []
tags:
    - 'task-grouping,taskbar'
---
A new feature in Windows XP is the ability to group several instances of the same application as one task icon. This keeps the taskbar from getting all cluttered when working with several applications. It also helps in the situations where Internet Explorer is scripted by a malicious site to start a zillion instances of itself making it easy to close all down. But if used to having 3-4 Internet Explorers or Notepads running at a time without wanting them to be grouped together then one can get annoyed.  
  
 To disable the task grouping completely:

1. Right click the Start-button and select "Properties"
2. Select the "Taskbar"-tab
3. Untick "Group similar taskbar buttons"
 
 One can also disable it through the registry with this DWORD value:
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
 >  TaskbarGlomming = 0 (Default = 1)

 One can change the behavior of the task grouping:
> Group by age(oldest first) = 0  
>  Group by size(largest first) = 1  
>  Group when size 2 = 2   
>  Group when size 3 = 3   
>  Group when size n = n   
>   
>  \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\Advanced\]  
>  TaskbarGroupSize = 8 (Default = 0)

 More Info [MS KB281628](http://support.microsoft.com/kb/281628 "How to Change the Behavior of Taskbar Grouping [Q281628]")  
  
 Related [Configure the taskbar](/article/windows-taskbar.html)