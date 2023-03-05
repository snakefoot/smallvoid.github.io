---
title: WebClient
date: '2003-06-05T21:25:53+02:00'
status: publish
permalink: /article/winnt-services-webclient.html
author: Snakefoot
excerpt: 'Description and recommended settings for the WebClient service.'
type: post
id: 615
category:
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
    - 'Services Guide'
tag:
    - webdav
post_format: []
tags:
    - webdav
---
##### Description:

 Enables Windows-based programs (Like the Web Publishing Wizard) to create, access, and modify Internet-based files on Internet file servers using the WebDAV protocol. The WebDAV protocol is a file access protocol described in eXtendible Markup Language (XML) that travels over the Hypertext Transfer Protocol (HTTP).  
  
 Note this service interferes when accessing remote files and can cause long delays when accessing My Network Places. More Info [MS KB832161](http://support.microsoft.com/kb/832161 "You experience a delay when you use your Windows XP computer to log on to a domain or to connect to a network resource [Q832161]")  
  
 Note XP SP2 disables the use of the less secure "Basic Authentication", but one can enable it by setting this DWORD:
> HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\WebClient \\Parameters\]  
>  UseBasicAuth = 1  
>   
>  Note in Windows Vista the value 1 means that it will allow basic authentication for only SSL sites, and the value 2 means that it will allow basic authentication for all sites.  
>   
>  More Info [MS KB841215](http://support.microsoft.com/kb/841215 "You cannot connect to a document library in Windows SharePoint Services by using Windows shell commands or by using Explorer View [Q841215]")

 Note if the WebDAV folder contains more than a 1000 files, then XP might fail to enumerate all the files in the folder, as there is a max size limit when downloading the directory listing:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\WebClient \\Parameters\]  
>  FileAttributesLimitInBytes = 10000000 (Max size in bytes for a directory listing)  
>   
>  More Info [MS KB912152](http://support.microsoft.com/kb/912152 "You cannot access a WebDAV Web folder from a Windows XP-based client computer")

 Note if trying to access a file larger than 50 MByte in a WebDAV folder, then XP might fail to download the file, as there is a max size limit when downloading files:
> \[HKEY\_LOCAL\_MACHINE \\SYSTEM \\CurrentControlSet \\Services \\WebClient \\Parameters\]  
>  FileSizeLimitInBytes = 50000000 (Max size in bytes for a file download)  
>   
>  More Info [MS KB900900](http://support.microsoft.com/kb/900900 "You may receive an error message when you try to download a file that is larger than 50000000 bytes from a Web folder on a computer that is running Windows XP with Service Pack 1 or with Service Pack 2")

   
 Related [Mapping WebDAV folder as a network drive letter](/article/winnt-webdav-network-drive.html)
 
##### Recommended State:

- Disabled.

##### Default State:

- Win7: Manual.
- Vista: Automatic.
- Win2k3: Disabled.
- WinXP: Automatic.

##### Process Name:

- [svchost.exe -k LocalService](/article/winnt-services-wrapper.html) (WebClient)

##### Supports:

- None

##### Depends:

- WebDav Client Redirector