---
title: 'Mapping FTP server as a network drive letter'
date: '2007-09-01T09:19:37+02:00'
status: publish
permalink: /article/ftp-map-network-drive.html
author: Snakefoot
excerpt: 'Utilities for mounting a FTP folder as a mapped netwok drive.'
type: post
id: 737
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - drive-mount
    - file-system
    - ftp
    - ftp-client
    - network-drive
post_format: []
tags:
    - 'ftp,ftp-client,network-drive,file-system,drive-mount'
---
Emulating a FTP server as a mapped network drive is not trivial, as the FTP server doesn't supply all the file system operations required by a network drive. Forexample to open a file placed on a FTP server, then the entire file has to be downloaded completely first, as FTP doesn't provide read and write locking capability. This can lead to funny behavior if background services (Anti-Virus, Movie-Preview) wants to scan the files on the network drive.  
  
 The following freeware utilities can mount a FTP server as a network drive:
- [Novell Netdrive](http://smallvoid.orgfree.com/?file=netdrive.zip) - [User Guide](http://www.novell.com/documentation/ifolder21/netdrive/data/a2iii88.html "Novell NetDrive 4.1 User Guide") (Not freeware but [abandonware](http://www.novell.com/coolsolutions/qna/999.html))
- [FTP Drive](http://www.killprog.com/fdrve.html)
- [Bdrive - NetDrive](http://netdrive.net/) - Free for home use, also supports WebDAV.
 
 There also exist utilities one can pay for:
- [WebDrive](http://www.webdrive.com/) (Recommended)
- [TeamDrive Client](http://teamdrive.net/)
- [SftpDrive](http://www.sftpdrive.com/)
 
 Note if using Windows XP or later, then consider [mapping a WebDAV folder as network drive](/article/winnt-webdav-network-drive.html) instead.  
  
 Related [Adding FTP server / WebDAV folder as network place](/article/winnt-web-network-place.html)