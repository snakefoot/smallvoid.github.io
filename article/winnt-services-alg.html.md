---
title: 'Application Layer Gateway'
date: '2003-06-05T23:16:28+02:00'
status: publish
permalink: /article/winnt-services-alg.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Application Layer Gateway service.'
type: post
id: 522
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - internet-connection-sharing
    - network-router
post_format: []
tags:
    - 'internet-connection-sharing,network-router'
---
##### Description:

 Allows 3rd party software plugins to interface with the Internet Connection Sharing (ICS). For example if having a plugin that allows a 3rd party protocol to pass through the router functionality of ICS.  
  
 Note one of these 3rd party protocols is the MSN Messenger, and if this service is disabled the application cannot pass through the ICS.  
  
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- alg.exe (ALG)

##### Supports:

- [Internet Connection Sharing (ICS)](/article/winnt-services-sharedaccess.html)

##### Depends:

- none