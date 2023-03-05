---
title: 'DFS Replication'
date: '2007-07-17T02:13:15+02:00'
status: publish
permalink: /article/winnt-services-dfsr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the DFS Replication service.'
type: post
id: 665
category:
    - 'Services Guide'
tag: []
post_format: []
tags:
    - ''
---
##### Description:

 Replicates files among multiple PCs keeping them in sync. On Client, it is used to roam folders between PCs; on server, it is used to provide high availability and local access across a wide area network (WAN). If the service is stopped, distributed file system (DFS) replication does not occur, and the files on the server become out-of-date. If the service is disabled, any services that explicitly depend on it will not start.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- DFSR.exe (DFSR)

##### Supports:

- none

##### Depends:

- [COM+ Event System](/article/winnt-services-eventsystem.html)