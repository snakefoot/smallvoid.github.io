---
title: 'Thread Ordering Server'
date: '2007-07-17T02:16:39+02:00'
status: publish
permalink: /article/winnt-services-threadorder.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Thread Ordering Server service.'
type: post
id: 707
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Provides ordered execution for a group of threads within a specific period of time. It ensures that each client thread runs once during the specific period and in relative order.  
  
 More Info [MSDN - Thread Ordering Service](http://msdn2.microsoft.com/en-us/library/ms686752.aspx)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (THREADORDER)

##### Supports:

- none

##### Depends:

- none