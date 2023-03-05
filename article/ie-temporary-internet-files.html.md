---
title: 'Configure the Temporary Internet Files cache'
date: '2002-02-02T00:26:07+01:00'
status: publish
permalink: /article/ie-temporary-internet-files.html
author: Snakefoot
excerpt: 'How to configure the size of the Temporary Internet Files cache.'
type: post
id: 132
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - cache
    - free-disk-space
    - temporary-internet-files
post_format: []
tags:
    - 'temporary-internet-files,cache,free-disk-space'
---
Both Internet Explorer and Outlook Express can have trouble with a large Temporary Internet File cache (Index.dat). Leading to problems in loading web pages and sending emails with large attachments.

##### Clear Temporary Internet Files

 Sometimes clearing the Temporary Internet Files cache can solve problems with loading of web pages. To clear the Temporary Internet Files go here:
1. Open **Control Panel** and double-click **Internet Options**
2. Select the **General**-tab and press the **Delete Files...**-button (Inside "Temporary Internet Files"-group)
 
 Note if having trouble loading a single page, then one can try to hold down the CTRL-key and click the refresh button (or press F5). This is easier than starting to empty the whole cache.  
  
 Note if having trouble with outdated pages, then it might also be caused by a proxy server used for fast remote caching. It is possible that the cache of the proxy server contains outdated pages. One can configure the use of a proxy server in Internet Explorer, but some times the Internet Service Provider (ISP) will setup a proxy server, which will be used no matter what, to save bandwidth.
 
##### Resize Temporary Internet Files cache

 To configure the amount of space assigned to the Temporary Internet Files go here (Assign about 10 MByte):
1. Open **Control Panel** and double-click **Internet Options**
2. Select the **General**-tab and press the **Settings...**-button (Inside "Temporary Internet Files"-group)

##### Move Temporary Internet Files folder

 One can also move the Temporary Internet Files so they don't cause [file fragmentation](/article/defrag-hard-disk-partition.html), because of the files are constantly created and deleted.  
1. Open **Control Panel** and double-click **Internet Options**
2. Select the **General**-tab and press the **Settings...**-button (Inside "Temporary Internet Files"-group)
3. Press the **Move Folder...**-button.
 
 One can also move the Temporary Internet Files, by using the registry:
 
> \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft\\ Windows\\ CurrentVersion\\ Explorer\\ User Shell Folders\]  
> \[HKEY\_CURRENT\_USER\\ Software\\ Microsoft\\ Windows\\ CurrentVersion\\ Explorer\\ Shell Folders\]  
>  Cache = "Z:\\"

 Related [Empty Internet Explorer Temporary File Cache at exit](/article/ie-empty-temporary-internet-files.html)