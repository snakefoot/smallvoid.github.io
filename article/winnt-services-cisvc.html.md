---
title: 'Indexing Service'
date: '2000-07-23T02:15:23+02:00'
status: publish
permalink: /article/winnt-services-cisvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Indexing service.'
type: post
id: 552
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - file-search
post_format: []
tags:
    - file-search
---
##### Description:

 Indexes contents &amp; properties of files on local &amp; remote computers; provides rapid access to files through flexible querying language.  
 File searches are slow when done without an index as it requires a lot of disk activity, because all files has to be opened and scanned. With an index the scan only have to be performed once, and then use the optimized index file for future file searches.  
 The Indexing Service maintains the index by detecting when the computer is idle, and then launches Cidaemon.exe, which checks whether any new files have arrived or existing files have been changed.  
  
 Note if using the indexing service, then one should make sure that: - Index only NTFS partitions as the journal filesystem makes maintenance of the index quick. FAT partitions requires that the Indexing Service scans the entire partition every time to maintain the index.
- Exclude Directories containing temporary files from the index (Like [TEMP](/article/temporary-directory.html) and [Temporary Internet Files](/article/ie-temporary-internet-files.html))
 
 More Info [MS KB317586](http://support.microsoft.com/kb/317586 "HOW TO: Optimize Indexing Service Performance in Windows 2000 [Q317586]")  
  
##### Recommended State:

- Disabled, if not wanting to use extra resources to get a faster file search.

##### Default State:

- Win2k Server : Manual.
- Win2k Pro : Disabled.
- WinXP : Manual.
- Win2k3 : Manual.

##### Process Name:

- cisvc.exe (cisvc)

##### Supports:

- None

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)