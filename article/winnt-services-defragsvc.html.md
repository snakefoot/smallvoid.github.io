---
title: 'Disk Defragmenter - Optimize Drives'
date: '2009-09-17T21:33:40+02:00'
status: publish
permalink: /article/winnt-services-defragsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Disk Defragmenter/Optimize Drives Service.'
type: post
id: 799
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - defrag
post_format: []
tags:
    - defrag
---
##### Description:

 Helps the computer run more efficiently by optimizing files on storage drives (Ex. defragmentation)  
  
 Used to perform scheduled disk defragmentation. To configure the scheduled task controlling this service:
1. Control Panel -&gt; System and Security -&gt; Administrative Tools -&gt; Task Scheduler
2. Task Scheduler Library -&gt; Microsoft -&gt; Windows -&gt; Defrag -&gt; ScheduleDefrag

##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- [svchost.exe -k defragsvc](/article/winnt-services-wrapper.html) (defragsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)