---
title: 'Configure the file search to include all files types'
date: '2003-01-10T20:44:52+01:00'
status: publish
permalink: /article/winnt-file-search-filter.html
author: Snakefoot
excerpt: 'Change whether the file search assistant should look through only registered file types or all files.'
type: post
id: 407
category:
    - Desktop
    - Desktop
tag:
    - file-search
    - indexing-service
post_format: []
tags:
    - 'file-search,indexing-service'
---
Windows XP changes the filesearch functionality to only to look for registered files. This is done to make the search quicker and more userfriendly. But it can be annoying for users who are expecting that all files are searched.  
  
 To make it search all files do the following:

1. Open **Computer Management** (Right-click "My Computer" and select "Manage")
2. Expand **Services and Applications** and right-click **Indexing Service** and choose "Properties". ([Indexing Service](/article/winnt-services-cisvc.html) don't have to run for this setting to work)
3. Select the **Generation**-tab and check **Index files with unknown extensions** and press **Ok**
4. The above steps should be reflected in this DWORD registry key:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Control \\ContentIndex\]  
>  FilterFilesWithUnknownExtensions = 1 (Default = 0)  
>   
>  More Info [MS KB309173](http://support.microsoft.com/kb/309173 "Using the "A Word or Phrase in the File" Search Criterion May Not Work [Q309173]")
 
 To make it use the classic search without assistant, set this STRING value in the registry (Will make it stop accessing the Internet for search tips):
 > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Explorer \\CabinetState\]  
 >  Use Search Asst = "no"

 Credits [ntfaq.com](http://ntfaq.com/)