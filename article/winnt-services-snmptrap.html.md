---
title: 'SNMP Trap'
date: '2007-07-17T02:16:07+02:00'
status: publish
permalink: /article/winnt-services-snmptrap.html
author: Snakefoot
excerpt: 'Description and recommended settings for the SNMP Trap service.'
type: post
id: 701
category:
    - 'Services Guide'
    - 'Services Guide'
tag:
    - SNMP
post_format: []
tags:
    - SNMP
---
##### Description:

 Receives trap messages generated by local or remote Simple Network Management Protocol (SNMP) agents and forwards the messages to SNMP management programs running on this computer. If this service is stopped, SNMP-based programs on this computer will not receive SNMP trap messages. If this service is disabled, any services that explicitly depend on it will fail to start.  
  
 More Info [SNMP (Wiki)](http://en.wikipedia.org/wiki/Simple_Network_Management_Protocol)
 
##### Recommended state:

- Manual

##### Default State:

- Manual

##### Proces name:

- snmptrap.exe (SNMPTRAP)

##### Supports:

- none

##### Depends:

- none