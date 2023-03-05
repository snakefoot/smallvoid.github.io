---
title: 'Using the services management snapin to change the service state'
date: '2003-07-30T01:10:37+02:00'
status: publish
permalink: /article/winnt-services-config.html
author: Snakefoot
excerpt: 'How to use the services management snapin to configure the state of the Windows services.'
type: post
id: 629
category:
    - Troubleshoot
    - Troubleshoot
    - Troubleshoot
tag:
    - windows-services
post_format: []
tags:
    - windows-services
---
1. Open the **Services**-snapin by pressing the **Start**-button and **Run...** this command:
   > Services.msc

   ![Service Management]({{ 'assets/images/services_mgmt.jpg' | relative_url }})
  
2. Double click the service you want to change (Here [Messenger](/article/winnt-services-messenger.html))  

   ![Service Properties]({{ 'assets/images/service_properties.jpg' | relative_url }})
    
3. In the **Startup Type**-dropdown select the desired state
4. If setting the service to **Disabled** or **Manual**, then press the **Stop**-button to deactivate the service.
5. If setting the service to **Automatic**, then press the **Start**-button to activate the service.
6. Press the **Ok**-button