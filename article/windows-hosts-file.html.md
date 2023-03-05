---
title: 'Use HOSTS file to ban ads and speedup DNS lookups'
date: '2001-04-04T21:50:41+02:00'
status: publish
permalink: /article/windows-hosts-file.html
author: Snakefoot
excerpt: 'How the HOSTS file can be used to customize the host name resolution.'
type: post
id: 218
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - dns
    - hosts-file
    - name-resolution
    - tcpip
post_format: []
tags:
    - 'name-resolution,tcpip,dns,hosts-file'
---
It is much easier to access the Internet when using domain-names like www.google.com, instead of needing to remember IP-addresses. The conversion of a domain-name to an IP-address is performed by the Domain Name System (DNS) and is also called [host name resolution](/article/windows-host-name-resolution.html). Your Internet Service Provider (ISP) is responsible for supplying the DNS.  
  
 It is possible to divert from the normal domain-name conversion supplied by your ISP, and instead specify your personal domain-name conversion. This is possible because before contacting the DNS, then the computer checks a special file named HOSTS whether it contains the domain-name and the corresponding IP-Address. The HOSTS file is a simple text file, which can be edited a text-editor like Notepad. The HOSTS file allows one to specify your own list of domains and their corresponding IP-Address.  
  
 The HOSTS file can be used to:

- Ban access to certain domains to avoid loading advertisements, thus making the Internet browsing quicker. 
  1. Find the domain (The address from where the advertisement is loaded from)
  2. Insert the this dummy IP along with the domain in the file:
     > 127.0.0.1 ad.linkexchange.com
  3. If having problems creating the ban file it might help to have this line in the top of the HOSTS file:
     > 127.0.0.1 localhost
  4. There is certain sites that provides pre-made HOSTS file for your convenience (and peril): 
      - [MVP's HOSTS File](http://www.mvps.org/winhelp2002/hosts.htm)
      - [SCoooBY's HOSTS File](http://www.geocities.com/drdole/)
      - [Eric L. Howes HOSTS Files](http://www.spywarewarrior.com/uiuc/index.html)
       
       Note an alternative way to ban advertisement is to use a firewall, as many firewalls includes advertisement blocking functionality, and its list of "bad" domains are updated regularly.
- Speedup DNS lookups by not needing to contact the DNS server, thus making the Internet browsing quicker. 
  1. Find the IP for domain (Can be done by pinging the existing domain)
  2. Insert the discovered IP along with the domain in the file:
     > 206.132.163.167 members.nbci.com
  3. There exists utilities to help you maintain your HOSTS files: 
      - [Alchemydev's FastDNS](http://smallvoid.orgfree.com/?file=fastdns36.zip) [Download Mirror](http://www.geocities.com/drdole/Apps/FastDnsv3.6.zip)
      - [abelhadigital.com HostMan](http://www.abelhadigital.com/)
       
       Note the DNS lookup tweak should only be done for a limited set of frequently used domains (like mail server), because if the domain changes IP address then the domain will become inaccessible.
 
 The HOSTS file is usually found here:
- Windows 9x = C:\\Windows\\
- Windows NT-2000 = C:\\Winnt\\System32\\Drivers\\etc\\
- Windows XP = C:\\Windows\\System32\\Drivers\\etc\\
- Linux/BSD/Solaris/Unixes = /etc/
- BEOS = /boot/beos/etc/
 
 Note Win2k/XP/2k3 have a new feature called [DNS Client](/article/winnt-services-dnscache.html) that caches DNS lookups. This makes the DNS lookup tweak unneeded as it is automatically is performed by this new feature. Though there have been several reports that if using a large HOSTS file to ban advertisement, then the [DNS Client](/article/winnt-services-dnscache.html) will introduce slowdowns, and should be disabled if wanting to ban advertisements using the HOSTS file.  
  
 Note by default the HOSTS file only contains one active entry and that is "127.0.0.1 localhost". If having trouble with accessing a domain, then one can disable the HOSTS file effect by deleting or renaming the HOSTS file, and restart the browser(Sometime need to restart the system).  
  
 Note lately some hijackers have started to modify the HOSTS file to make redirects to a different site than intended. One can try to "lock" the HOSTS file by changing the file attributes to Read-Only, Hidden, System. If the file is placed on a NTFS partition then [change the NTFS permissions](/article/ntfs-access-control.html) for accessing the HOSTS file. Though if the hijacker is clever enough then it will have little trouble going around this "locking".  
  
 More Info [MS KB972034 - Reset hosts file to default](http://support.microsoft.com/kb/972034 "How do I reset the hosts file back to the default?")  
  
 Credits [mvps.org](http://www.mvps.org/winhelp2002/hosts.htm)