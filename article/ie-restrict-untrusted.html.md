---
title: 'Restrict Internet Explorer when not accessing trusted sites'
date: '2001-09-25T22:30:14+02:00'
status: publish
permalink: /article/ie-restrict-untrusted.html
author: Snakefoot
excerpt: 'Internet Explorer can be locked down so only trusted websites can activate ActiveX and use cookies for tracking.'
type: post
id: 283
category:
    - 'Internet Explorer (IE4)'
    - 'Internet Explorer (IE5)'
    - 'Internet Explorer (IE6)'
tag:
    - activex
    - cookies
    - security-zone
    - trusted-sites
post_format: []
tags:
    - 'trusted-sites,security-zone,activex,cookies'
---
Microsoft loves to makes sure everything is easy for the end user, and they loves when people uses the Microsoft invented ActiveX.  
  
 Sadly enough is ActiveX has proven to be very insecure, giving access to files on your hdd and executing commands and much more. Microsoft is still fighting to get it all fixed but until then one should try to avoid using ActiveX.  
  
 Companies loves to have a record of their users and log information about where they go, and therefore they like when we use cookies as it helps them in advertising. Privacy is not something which is thought much about.  
  
 By standard these things are allowed by default for all websites. One might consider to turn it around, by changing trusted sites to reflect the Internet Security and make Internet Security harsher.  
 Then if visiting sites which requires ActiveX and such which you like or want them to save password in cookies, then add them to trusted sites.

##### Configure IE to treat standard websites as insecure:

1. In Internet Explorer go to the **Tools**-menu and select **Internet Options...**
2. Go to the **Security**-tab and select the **Internet**-zone and press **Custom Level...**
3. Change the following settings (**bold** diverts from default setting "Medium"): 
  - ActiveX controls and plug-ins 
      - Download signed ActiveX controls - Prompt
      - Download unsigned ActiveX controls - Disable
      - Initialize and script ActiveX controls not marked as safe - Disable
      - Run ActiveX controls and plug-ins - Enable
      - Script ActiveX controls marked safe for scripting - Enable
  - Downloads 
      - File download - Enable
      - Font download - **Prompt**
  - Miscellaneous 
      - Access data sources across domains - Disable
      - Allow META REFRESH - Enable
      - Display mixed content - **Enable**
      - Don't prompt for client certificate selection when no certificates or only one certificate exists - Disable
      - Drag and drop or copy and paste files - **Prompt** ([MS KB888534](http://support.microsoft.com/kb/888534 "How to help protect against the Internet Explorer Click and Scroll security issue [Q888534]"))
      - Installation of desktop items - **Disable**
      - Launching programs and files in an IFRAME - Prompt
      - Navigate sub-frames across different domains - Enable
      - Software Channel Permissions - High safety
      - Submit nonencrypted form data - **Enable**
      - Userdata persistence - Enable (Required by Windows Update)
  - Scripting 
      - Active scripting - Enable (Javascript/VBScript)
      - Allow paste operations via script - **Disable** ([MS KB224993](http://support.microsoft.com/kb/224993 "How to Prevent Web Sites From Obtaining Access to the Contents of Your Windows Clipboard [Q224993]"))
      - Scripting of Java applets - Enable
  - User Authentication 
      - Logon - Automatic logon only in Intranet zone

##### Configure IE not to store cookies from standard website:

- Internet Explorer 5 
  1. In Internet Explorer go to the **Tools**-menu and select **Internet Options...**
  2. Go to the **Security**-tab and select the **Internet**-zone and press **Custom Level...**
  3. Change the following settings: 
      - Cookies - Allow Per-session Cookies (Not Stored)
- Internet Explorer 6 
  1. In Internet Explorer go to the **Tools**-menu and select **Internet Options...**
  2. Go to the **Privacy**-tab and set the level to **High**

##### Add a trusted site to IE:

1. In Internet Explorer go to the **Tools**-menu and select **Internet Options...**
2. Go to the **Security**-tab and select the **Trusted sites**-zone and press **Custom Level...**
  - In the **Reset to**-dropdown select "Medium" and press **Reset** and then press **Ok**
3. Go to the **Security**-tab and select the **Trusted sites**-zone and press **Sites...** to add the trusted site.  
  
  - Internet Explorer 6 users must also go to the **Privacy**-tab and press **Edit...** to allow cookies for the trusted site.
 
 More Info [MS KB182569](http://support.microsoft.com/kb/182569 "Description of Internet Explorer security zones registry entries [Q182569]")  
  
 Note if accessing your Hotmail from Outlook Express then you need to add "services.msn.com" to trusted sites or else it will ask for password and will not allow you to view your email.  
  
 Note like adding a trusted site to IE, then one can configure the **Restricted**-zone to "High", where **Active Scripting** is disabled, and use this to control websites:
- Add the website "msn.rad.com" to disable advertisements in MSN Messenger.
- Change [Outlook Express to open emails in restricted zone](/article/outlook-express-security-zone.html) to block virus.
 
 Related [Enable configuration of My Computer security zone](/article/my-computer-security-zone.html)  