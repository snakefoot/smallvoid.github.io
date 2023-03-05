---
title: 'Special Administration Console Helper'
date: '2003-09-21T18:56:57+02:00'
status: publish
permalink: /article/winnt-services-sacsvr.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Special Administration Console Helper service.'
type: post
id: 598
category:
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 The Special Administration Console (SAC) can connect to a machine, where this service is running. SAC can perform remote management tasks in case Windows on the machine stops functioning due to a Stop error message.  
  
 The SAC is an auxiliary Emergency Management Services command-line environment with the following main functions:
- Redirect Stop error message explanatory text.
- Restart the system.
- Obtain computer identification information.

##### Recommended State:

- Manual.

##### Default State:

- Manual

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (Sacsvr)

##### Supports:

- None

##### Depends:

- None