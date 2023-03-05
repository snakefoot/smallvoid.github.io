---
title: 'Remove the Shared Documents folder from My Computer'
date: '2002-01-01T20:38:16+01:00'
status: publish
permalink: /article/winnt-shared-documents.html
author: Snakefoot
excerpt: 'The shared documents folder allows multiple users to exchange documents, pictures and other files on the same computer.'
type: post
id: 406
category:
    - Desktop
tag:
    - shared-documents
post_format: []
tags:
    - shared-documents
---
A new feature of WinXP is being able to share documents between users through the icon "Shared Documents" in My Computer.  
  
 This feature can be disabled through the Group Policy if using WinXP Pro :

1. Start Menu -&gt; Run... -&gt; gpedit.msc
2. Go to User Configuration -&gt; Administrative Templates -&gt; Windows Components -&gt; Windows Explorer
3. Find the option "Remove Shared Documents from My Computer"
4. Double click the option and set it to "Enabled"
 
 The above policy is reflected in the following DWORD registry key (HKEY\_LOCAL\_MACHINE can also be used) :  
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Explorer\]  
>  NoSharedDocuments = 1 (No Folder = 1, Default = 0)  
>   
>  More Info [MS KB286727](http://support.microsoft.com/kb/286727 "The My Computer Icon Displays the My Documents Folders of Another User [Q286727]")

 Another way to do this is going to this registry entry:  
> \[HKEY\_LOCAL\_MACHINE \\SOFTWARE \\Microsoft \\Windows \\CurrentVersion \\Explorer \\My Computer \\NameSpace \\DelegateFolders\]

 And delete this sub key (Remember to make a backup before deleting) :  
> {59031a47-3f72-44a7-89c5-5595fe6b30ee}

 Credits [winsupersite.com](http://www.winsupersite.com/)  