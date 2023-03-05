---
title: 'Configure the name cache for faster file lookup'
date: '2000-01-01T18:50:34+01:00'
status: publish
permalink: /article/win9x-name-cache.html
author: Snakefoot
excerpt: 'How to change the role of the computer to be "Network Server".'
type: post
id: 88
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - disk-performance
    - file-cache
    - hard-disk-drive
post_format: []
tags:
    - 'file-cache,hard-disk-drive,disk-performance'
---
To avoid accessing the HDD to find a file. it caches the file name and location of the most recent used files and paths. To configure the size of this cache go to Control Panel -&gt; System -&gt; Performance -&gt; FileSystem and change the Role to "Network Server".  
  
[MS KB138012](http://support.microsoft.com/kb/138012 "Incorrect Settings for File System Performance Profiles [Q138012]") States that the original Win95 and with SP1 won't configure the cache properly. You can check this by opening REGEDIT and looking up the following registry key for the profile templates.

> \[HKEY\_LOCAL\_MACHINE\\ SOFTWARE\\ Microsoft\\ Windows\\ CurrentVersion\\ FS Templates\\ Server\]  
>  NameCache = a9 0a 00 00 (Will store 2729 filenames)  
>  PathCache = 40 00 00 00 (Will store 64 folders)

 You can also specify your own templates like the Server template. Add a new key like this one:  
> \[HKEY\_LOCAL\_MACHINE\\ SOFTWARE\\ Microsoft\\ Windows\\ CurrentVersion\\ FS Templates\\ MaxCache\]  
>  @ = "Max Cache"  
>  NameCache = 00 18 00 00 (Will store 6144 filenames)  
>  PathCache = 80 00 00 00 (Will store 204 folders)

 To see the settings you are currently using go to this registry key and check the same values:  
> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\Control \\FileSystem\]

- **NameCache** is used to store the most recently accessed filenames.
- **PathCache** is used to store the most recently accessed folders.
- **BufferIdleTimeout**, **BufferAgeTimeout**, and **VolumeIdleTimeout** controls the time between when changes are placed in the buffer to when they are written to the hard disk.