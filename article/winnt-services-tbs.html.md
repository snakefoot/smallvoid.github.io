---
title: 'TPM Base Services'
date: '2007-07-17T02:16:43+02:00'
status: publish
permalink: /article/winnt-services-tbs.html
author: Snakefoot
excerpt: 'Description and recommended settings for the TPM Base Services.'
type: post
id: 708
category:
    - 'Services Guide'
    - 'Services Guide'
tag: []
post_format: []
---
##### Description:

 Enables access to the Trusted Platform Module (TPM), which provides hardware-based cryptographic services to system components and applications. If this service is stopped or disabled, applications will be unable to use keys protected by the TPM.
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- Win7 - [svchost.exe -k LocalServiceAndNoImpersonation](/article/winnt-services-wrapper.html) (TBS)
- Vista - [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (TBS)

##### Supports:

- none

##### Depends:

- none