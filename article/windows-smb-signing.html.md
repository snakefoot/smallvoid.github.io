---
title: 'Description of SMB signing in the Microsoft Network'
date: '2003-09-19T21:16:55+02:00'
status: publish
permalink: /article/windows-smb-signing.html
author: Snakefoot
excerpt: 'How the security features in SMB signing can protect the network.'
type: post
id: 208
category:
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
    - 'File Sharing'
tag:
    - microsoft-network
    - network-performance
    - smb-signing
post_format: []
tags:
    - 'microsoft-network,smb-signing,network-performance'
---
The Server Message Block (SMB) protocol was developed jointly by Microsoft, IBM and Intel. SMB is used for providing and obtaining network file services, making it possible to copy files between networked computers. Security issues can arise if in a network with untrusted clients:

- **Man-in-the-middle attack**: The Intruder setup a network sniffer and intercept the traffic sent when a user copies a file from one computer to another. To keep the Intruder from being able to convert the intercepted traffic to a file again, one uses Mutual Authentication.
- **Active Message attack**: The Intruder replays intercepted traffic. To keep the Intruder from replaying the deletion of directory or similar, one uses Message Authentication.
 
 SMB signing includes the security features Mutual Authentication and Message Authentication. Though when enabling SMB signing one is also adding an overhead that can decrease file transfer performance with 10-15%. Therefore if performance is critical and located in a trusted network, then one can consider to disable SMB signing.  
  
 Note when having SMB signing enabled, then it will also add extra security when sending username and password over the network for authentication. Therefore if turning off SMB signing then one should especially consider [enforcing a higher password encryption level](/article/windows-password-encryption.html).  
  
 Related [Configure SMB signing in Win9x](/article/win9x-smb-signing.html)  
 Related [Configure SMB signing in WinNT+](/article/winnt-smb-signing.html)  