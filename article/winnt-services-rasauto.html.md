---
title: 'Remote Access Auto Connection Manager'
date: '2000-07-23T16:32:38+02:00'
status: publish
permalink: /article/winnt-services-rasauto.html
author: Snakefoot
excerpt: 'Description and recommended settings for the Remote Access Auto Connection Manager service.'
type: post
id: 577
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - dialup-modem
post_format: []
tags:
    - dialup-modem
---
##### Description:

 Automatically creates a connection to a remote network, whenever a program references a remote DNS or NETBIOS name or address.  
 The service can bring up a dialog which offers to make a dial-up or virtual private network (VPN) connection to a remote computer.  
  
 More Info [MS KB254181](http://support.microsoft.com/kb/254181 "Description of the Functions of Remote Access Auto Connection Manager Service and Autodial [Q254181]")  
  
##### Recommended State:

- Disabled, if not using a modem connection or a Virtual Private Network(VPN).
- Manual, if wanting such a connection automatically to be made when it is required.

##### Default State:

- Manual

##### Process Name:

- [svchost.exe -k netsvcs](/article/winnt-services-wrapper.html) (RasAuto)

##### Supports:

- None

##### Depends:

- [Remote Access Connection Manager](/article/winnt-services-rasman.html)
- [Telephony](/article/winnt-services-tapisrv.html)