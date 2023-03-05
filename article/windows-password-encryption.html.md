---
title: 'Description of password encryption in the Microsoft Network'
date: '2003-09-19T21:23:16+02:00'
status: publish
permalink: /article/windows-password-encryption.html
author: Snakefoot
excerpt: 'The different password encryption algorithms available in the Microsoft Network.'
type: post
id: 209
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
    - encryption
    - ntlm
    - ntlm2
    - password
    - windows-domain
post_format: []
tags:
    - 'password,encryption,ntlm,ntlm2,windows-domain'
---
When a user tries to access a resource(like a share) over the network, then an authentication is performed using the username and password, to make sure the user has access rights to the resource.  
 One of the first authentication protocols was the Password Authentication Protocol (PAP). It requires that the username and password is sent in plain text over the network, and thus allowing an eavesdropping intruder with a packet sniffer to obtain this information.  
  
 The Challenge/Response or Challenge-Handshake Authentication Protocol (CHAP) was invented to avoid revealing the secret of the username and password. This is done by using an encryption algorithm, which converts the username and password into a number (Called hashing), which is then sent over the network. The receiver compares the received number with the hashes of the accounts it knows, and if there is a match then access is granted. The level of encryption is dependent on how strong the hashing algorithm is:

- Lan Manager (LM) Authentication: The most compatible and used by DOS, Win3.1, OS/2, but also very insecure.
- WinNT Lan Manager (NTLM) Authentication: Supports 56 bit encryption and is somewhat secure if having a password change policy.
- WinNT Lan Manager Ver.2 (NTLM2 or NTLMv2) Authentication: Supports 128 bit encryption and an intruder will need a large amount of computer power to decrypt.
 
 There are several ways of decrypting the encrypted username and password:
- Brute Force, by hashing all possible usernames and passwords into numbers, and then compare the numbers with the one intercepted until a match is found (Requires that the Intruder knows the encryption algorithm). This works with weak hashing algorithms, which doesn't require much calculation, but strong hashing algorithms will require a lot of computer power(Years).
- Dictionary, by comparing the hashing of commonly used passwords (like beer-, family-, dog-names) with the intercepted until a match is found. This works with weak passwords which doesn't use both upper and lower case letter along with special characters like numbers.
 
##### LMCompatibility / LMCompatibilityLevel

 By default the most compatible authentication (LM) is used, but also the most insecure. To avoid making brute force attacks too easy, then one should consider forcing a higher encryption level if the clients connected to the network supports it. <table border="1" cellpadding="5"><tr><th>Level </th><th>Lan Manager Compatibility level</th><th>Remarks</th></tr><tr><td align="center">0 </td><td>Client uses LM and NTLM  
Domain Controller accepts LM, NTLM and NTLM 2 </td><td align="center">Win9x / WinNT4 Default  
No compatibility issues</td></tr><tr><td align="center">1 </td><td>Client uses NTLM2 if possible else LM and NTLM  
Domain Controller accepts LM, NTLM, NTLM 2 </td><td align="center">Win2k SP3 / WinXP Default  
No compatibility issues</td></tr><tr><td align="center">2 </td><td>Client uses NTLM2 if possible else NTLM  
Domain Controller accepts LM, NTLM, NTLM 2 </td><td align="center">Win2k3 Default  
Require Samba2+  
Win9x Server fails</td></tr><tr><td align="center">3 </td><td>Client only uses NTML2  
Domain Controller accepts LM, NTLM, NTLM 2 </td><td align="center">Vista Default  
Require Samba3+  
Win9x Server fails</td></tr><tr><td align="center">4 </td><td>Client uses NTLM2 if possible else NTLM  
Domain Controller accepts NTLM, NTLM 2 </td><td align="center">Require Samba2+  
Win9x Server fails</td></tr><tr><td align="center">5 </td><td>Client only uses NTLM2  
Domain Controller accepts only NTLM 2 </td><td align="center">Require Samba3+  
Win9x Server fails</td></tr></table>

  
 Note NTLMv2 was introduced with WinNT4 SP4 (Made it work with SP6a) and is therefore not supported by previous Windows version. (Win95/98/Me requires Directory Services Client to support NTLM and NTLM2).
 
<a name="NtlmMinSec"></a>
##### NtlmMinClientSec/NtlmMinServerSec

 The Lan Manager Security Support Provider (SSP) can be configured to require certain security levels before accepting a connection: - 0x00000010 : Message Integrity (Demands Signing before connection is made)
- 0x00000020 : Message Confidentiality (Demands Encryption before connection is made)
- 0x00080000 : NTLM 2 Session security (Demands NTLM2 Authentication)
- 0x20000000 : 128-bit encryption (Demands message confidentiality of 128 bit)
- 0x80000000 : 56-bit encryption (Demands message confidentiality of 56 bit)
 
 Note the 128 bit encryption level is only available if the installation satisfies the United States export regulations.  
  
 Note client and server should be configured to require the same level of security, or else there is a high probability that the connection will fail.  
  
 Note if connecting to Samba 2.2.8a servers, then one should set the client security level (NtlmMinClientSec) to zero or else the client will not be able to connect. Samba 3+ is able to support 0x0080000.  
  
 Related [Configure Password Encryption level in Win9x](/article/win9x-password-encryption.html)  
 Related [Configure Password Encryption level in WinNT+](/article/winnt-password-encryption.html)  
  
 More Info [MS Technet - Most Misunderstood Windows Security Setting](http://technet.microsoft.com/en-us/magazine/cc160954.aspx "Security Watch - The Most Misunderstood Windows Security Setting of All Time (August 2006)")  
 More Info [MS KB147706](http://support.microsoft.com/kb/147706 "How to Disable LM Authentication on Windows NT [Q147706]")  
 More Info [MS KB175641](http://support.microsoft.com/kb/175641 "LMCompatibilityLevel and Its Effects [Q175641]")  
 More Info [MS KB239869](http://support.microsoft.com/kb/239869 "How to Enable NTLM 2 Authentication [Q239869]")  
  
 Related [Description of SMB packet signing](/article/windows-smb-signing.html)  
  
 Credits [Eric Glass](http://davenport.sourceforge.net/ntlm.html "The NTLM Authentication Protocol")