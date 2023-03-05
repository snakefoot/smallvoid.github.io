---
title: 'Configure the Attachment Manager in Windows XP SP2'
date: '2006-10-10T00:22:39+02:00'
status: publish
permalink: /article/ie-attachment-manager.html
author: Snakefoot
excerpt: 'Windows XP SP2 includes the ability to mark files downloaded from the Internet as insecure and block access to them.'
type: post
id: 291
category:
    - 'Internet Explorer (IE6)'
    - 'Internet Explorer (IE7)'
    - Tips
tag:
    - alternative-data-stream
    - attachment-execution-services
    - attachment-manager
    - ntfs
    - security-zone
    - trusted-sites
post_format: []
tags:
    - 'attachment-manager,attachment-execution-services,trusted-sites,security-zone,ntfs,alternative-data-stream'
    - 'attachment-manager,attachment-execution-services,trusted-sites,security-zone,ntfs,alternative-data-stream'
---
Windows XP SP2 includes a new feature called Attachment Manager, which adds a security prompt when trying to open files marked as being downloaded from the Internet or received as e-mail attachments.  
  
 When an application (Web-Browser, E-mail client, etc.) saves a downloaded file on a disk formatted with NTFS, then it can update the meta data for the file with the zone (Internet- / Restricted-zone) it was downloaded from. The meta data is saved as an Alternate Data Stream (ADS), which is a feature of NTFS where the same filename can be used to cover multiple data streams. More Info [MS KB105763](http://support.microsoft.com/kb/105763 "How To Use NTFS Alternate Data Streams").  
  
 When opening a file with an ADS that says it is from the Internet zone, then the Attachment Execution Services (AES) is activated. It recognizes the following 3 categories of files:

- High Risk - Will block the file from being opened, when the file is from the restricted-zone:

  > *Windows Security Warning:  
  >   
  >  Windows found that this file is potentially harmful. To help protect your computer, Windows has blocked access to this file.*

- Moderate Risk - Will prompt with a warning, before the file is opened, when the file is from the internet-zone:
  > *Open File - Security Warning:  
  >   
  >  The publisher could not be verified. Are you sure you want to run this software?*
- Low Risk - Will open the file with no nags

##### Ways of getting rid of the warning when opening a file:

- If the file is placed on your local machine, then you can unblock the file and remove the zone-marking with one of the following methods: 
  - Right-click the blocked file, and select **Properties**, and on the **General**-tab, click **Unblock**
  - When opening a moderate risk file, the warning dialog will include the option **Always ask before opening this file**. Clearing this option will remove the zone-marking for that file.
- If the file is placed on a UNC path (ex. \\\\local\\file.txt), then one can activate "Include all network paths (UNCs)" for the "Local Intranet"-zone 
  - Internet Explorer 7 users may need to uncheck the "Automatically detect intranet network" option first
- If the file is placed on a trusted network drive, then you can add the network drive, IP-address or the UNC to the list of sites for the "Local Intranet"-zone
- If the file-type is not considered dangerous (ex. mp3), then you can add the file-extension to the list of "LowRiskFileTypes"

##### Products integrated with the Attachment Manager

 The Attachment Manager is integrated into the following products, so when downloading files then it will perform zone-marking of the files received:
- Internet Explorer will mark downloaded files according to the website being in the [Internet Zone](/article/ie-restrict-untrusted.html)/Restricted Zone.
- Outlook Express &amp; Outlook will by default treat attachments as coming from the [Restricted Zone](/article/outlook-express-security-zone.html).
- Windows Messenger &amp; MSN Messenger &amp; Live Messenger will by default treat received files as coming from the Restricted Zone.
- Firefox 3 will mark downloaded files.

##### Settings to configure the Attachment Manager

 There are different [group policies](/article/winnt-group-policy-registry.html), which can be used to configure the attachment manager, which can be found here:
  > User Configuration \\Administrative Templates \\Windows Components \\Attachment Manager

- **Default risk level for file attachments** - This controls how to treat files that are zone-marked and not found in the built-in lists of known filetypes. By default it treats unknown file as "Moderate Risk".
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Associations\]  
  >  DefaultFileTypeRisk = 6151 (High = 6150, Moderate = 6151, Low = 6152)
- **Do not preserve zone information in file attachments** - This controls whether the Attachment Manager should zone-mark files downloaded from the Internet. By default zone-marking is enabled.
> \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Attachments\]  
  >  SaveZoneInformation = 1 (On = 1, Off = 2)
- **Inclusion list for low, moderate, and high risk file types** - This allows one to extend the built-in lists of known filetypes and override their default security category. By default the custom inclusion lists are not configured:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Associations\]  
  >  HighRiskFileTypes = ""  
  >  ModRiskFileTypes = ""  
  >  LowRiskFileTypes = ".mp3 .wma .jpg"
- **Trust logic for file attachments** - There are certain trusted file handlers like Notepad, and when a Moderate Risk file is opened with Notepad, then it is considered Low Risk. It possible to configure whether it should take the file handlers into consideration. By default it trusts the file handler:
  > \[HKEY\_CURRENT\_USER \\Software \\Microsoft \\Windows \\CurrentVersion \\Policies \\Attachments\]  
  >  UseTrustedHandlers = 2 (Filetype = 1, Handler = 2, Both = 3)
 
 Note it is possible to disable the checking of zone-markings completely by setting this [environment variable](/article/winnt-environment-variables.html):
> \[HKEY\_CURRENT\_USER \\Environment\]  
>  SEE\_MASK\_NOZONECHECKS = "1"  
>   
>  More info [MS KB889815](http://support.microsoft.com/kb/889815 "The Open File - Security Warning dialog box is displayed when you try to silently install a hotfix or an update by using a Visual Basic script in Windows XP Service Pack 2 [Q889815]")

 More info [MS KB815141](http://support.microsoft.com/kb/815141 "Internet Explorer Enhanced Security Configuration changes the browsing experience [Q815141]")  
 More info [MS KB875353](http://support.microsoft.com/kb/875353 "How to use the Security Alert dialog box in Windows XP Service Pack 2 and Windows XP Tablet PC Edition 2005 [Q875353]")  
 More info [MS KB883260](http://support.microsoft.com/kb/883260 "Description of how the Attachment Manager works in Windows XP Service Pack 2 [Q883260]")  