---
title: 'NT LM Security Support Provider (SSP)'
date: '2000-06-06T15:43:24+02:00'
status: publish
permalink: /article/winnt-services-ntlmssp.html
author: Snakefoot
excerpt: 'Description and recommended settings for the NT LM Security Support Provider service.'
type: post
id: 570
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - ntlm
    - ntlm2
post_format: []
tags:
    - 'ntlm,ntlm2'
---
##### Description:

 Local Security Authority (LSA) for the system (The actual service name is only used for historical reasons). The LSA handles all authentication before a user is allowed to access a resource, which can be done in several ways:
- [NTLM - LM, NTLM and NTLMv2](/article/windows-password-encryption.html)
- Kerberos
- SChannel - SSL &amp; TLS
- Digest

##### Recommended State:

- Manual.

##### Default State:

- Manual.

##### Process Name:

- [lsass.exe](/article/winnt-services-wrapper.html) (NtLmSsp)

##### Supports:

- [Telnet](/article/winnt-services-telnet.html) (WinXP/Win2k3 only)

##### Depends:

- None