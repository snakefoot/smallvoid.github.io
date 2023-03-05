---
title: BranchCache
date: '2009-09-16T11:37:49+02:00'
status: publish
permalink: /article/winnt-services-peerdistsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the BranchCache Service.'
type: post
id: 798
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - branchcache
post_format: []
tags:
    - branchcache
---
##### Description:

 This service caches network content from peers on the local subnet.  
  
 New feature that allows branch-offices to cache data from the main-office locally, to minimize traffic and increase speed.  
  
 More Info [Microsoft Technet](http://technet.microsoft.com/en-us/network/dd425028.aspx "BranchCache")
 
##### Recommended state:

- Manual

##### Default State:

- Windows 8 Pro: Manual
- Windows 7 Pro: Manual

##### Proces name:

- [svchost.exe -k PeerDist](/article/winnt-services-wrapper.html) (PeerDistSvc)

##### Supports:

- none

##### Depends:

- none