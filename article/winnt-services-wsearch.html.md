---
title: 'Windows Search'
date: '2007-07-17T02:18:27+02:00'
status: publish
permalink: /article/winnt-services-wsearch.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Windows Search service.'
type: post
id: 728
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - file-search
post_format: []
tags:
    - file-search
---
##### Description:

 Provides content indexing and property caching for file, email, and other content (via extensibility APIs). If the service is stopped or disabled, the Explorer will not be able to display virtual folder views of items, and search in the Explorer will fall back to item-by-item slow search.  
  
 The index service is also required to support saved searches like the "Recently Changed" search folder, which actually specifies a search query that is triggered when opening the directory. Note if one deletes an item from a search folder, then one is actually deleting the actual item, and not removing the item from the search result.  
  
 Note if SearchIndexer.exe runs wilds and uses 100% CPU or constantly says "Waiting to receive indexing status...", then it can have different causes:
- Hard drive is failing, and causes faulty reads. Open "My Computer" and check each partition for errors by right-clicking the drive and selecting Properties, and on the Tools-fan press "Check Now"
- Search Indexes has become corrupt and causes infinite loops. Open "Control Panel" and open "Indexing Options" and press Advanced-button. Press the "Restore Defaults"-button to restore your index to its original state. 
  - If this is not possible then open the registry and set the following registry key (And restart Windows):
    > \[HKEY\_LOCAL\_MACHINE \\ SOFTWARE \\ Microsoft \\ Windows Search\]  
    >  SetupCompletedSuccessfully = 0

##### Recommended state:

- Automatic

##### Default State:

- Automatic

##### Proces name:

- searchindexer.exe (WSearch)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)