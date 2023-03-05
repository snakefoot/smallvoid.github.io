---
title: 'Software Protection'
date: '2009-09-26T01:05:40+02:00'
status: publish
permalink: /article/winnt-services-sppsvc.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Software Protection service.'
type: post
id: 816
category:
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Enables the download, installation and enforcement of digital licenses for Windows and Windows applications. If the service is disabled, the operating system and licensed applications may run in a notification mode. It is strongly recommended that you not disable the Software Protection service.
 
##### Recommended state:

- Automatic (Delayed Start)

##### Default State:

- Automatic (Delayed Start)

##### Proces name:

- sppsvc.exe (sppsvc)

##### Supports:

- none

##### Depends:

- [Remote Procedure Call (RPC)](/article/winnt-services-rpcss.html)