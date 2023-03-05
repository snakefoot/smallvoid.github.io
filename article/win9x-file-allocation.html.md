---
title: 'Configure the file allocation unit to minimize file fragmentation.'
date: '2000-01-01T19:53:46+01:00'
status: publish
permalink: /article/win9x-file-allocation.html
author: Snakefoot
excerpt: 'How to configure the size of continuous space it will look for when performing file allocation.'
type: post
id: 93
category:
    - 'Tweak Performance'
    - 'Tweak Performance'
    - 'Tweak Performance'
tag:
    - cluster-size
    - defrag
post_format: []
tags:
    - 'cluster-size,defrag'
---
Windows 9x improves MS-DOS way of allocation disk space for a file, by only using cluster chain that are larger than 500 KBytes. This allows the file to grow without becoming fragmented right away. If Windows 9x cannot find continuous space larger than 500 KBytes, then it falls back to the MS-DOS behavior and uses the first available space it can find with [file fragmentation](/article/defrag-hard-disk-partition.html) to follow.  
  
 This allocation can be configured with the following DWORD:

> \[HKEY\_LOCAL\_MACHINE \\System \\CurrentControlSet \\control \\FileSystem\]  
>  ContigFileAllocSize = 512 (Default=500)

 If using the computer to write large files it can be recommended to set this to 1024 or more. Of course it can get too big, so it might always fall back to the MS-DOS behavior.