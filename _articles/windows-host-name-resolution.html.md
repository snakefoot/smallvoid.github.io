---
title: 'Description of host name resolution order'
date: '2004-10-10T21:47:10+02:00'
permalink: /article/windows-host-name-resolution.html
author: Snakefoot
excerpt: 'Description of the different ways Windows can convert a logical network name to a physical address.'
type: post
id: 217
categories:
    - windows-95_network
    - windows-98_network
    - windows-me_network
    - windows-nt4_network
    - windows-xp_network
    - windows-2000_network
    - windows-2003_network
tags:
    - dns
    - hosts-file
    - lmhosts
    - name-resolution
    - netbios
    - tcpip
    - wins
---
In a computer-network each computer have a unique physical address, but the physical address can be difficult to use, so instead one gives each computer a name (logical address). This introduces the problem of converting the logical address to the physical address, also called host name resolution. There are different methods available to perform this resolution:

- TCPIP 
  - [HOSTS](/article/windows-hosts-file.html) file. Uses a text-file placed locally to perform the resolution.
  - DNS. Sends a resolution-message to a Domain Name Server (DNS) and it performs the resolution.
- NetBIOS 
  - LMHOSTS file. Uses a text-file placed locally to perform the resolution. More Info <a href="https://www.bing.com/search?q=KB%20101927%20Q101927" rel="nofollow" title="The Lmhosts File for TCP/IP in Windows [Q101927]">MS KB101927</a>
  - Broadcast. Sends a resolution-message to every computer in the network. Bad for networks with many computers.
  - WINS. Sends a resolution-message to a NetBIOS Name Server (NBNS) aka. Windows Internet Naming Service (WINS) and it performs the resolution.
 
 There are different ways available for how to order the different methods. When a method fails to convert the logical-address to a physical-address within the timeout, then the next in the order is used until one succeeds or all fails. One should use the method-order that introduces the fewest timeouts and minimizes broadcasts and doesn't have a single point of failure.
- TCPIP-DNS: The default setting for Windows installations is to use DNS first.
- NetBIOS (**H**)ybrid-Node: The default setting when using NetBIOS first and have WINS configured.
- NetBIOS (**M**)ixed-Node: Broadcast is used in local subnet and WINS used to reach computers in remote subnet.
- NetBIOS (**P**)oint To Point-Node: When the WINS stops responding the whole network is down.
- NetBIOS (**B**)broadcast-Node: The default setting when using NetBIOS first and don't have WINS configured (Introduces a lot of resolution-traffic when on a large network)
 
<table border="1">
<tr><th>TCPIP-DNS</th> <th>(H)ybrid-Node</th> <th>(M)ixed-Node</th> <th>(P)oint To Point-Node</th><th>(B)roadcast-Node</th></tr>
<tr><td>HOSTS file</td> <td>NetBIOS name cache</td> <td>NetBIOS name cache</td> <td>NetBIOS name cache</td> <td>NetBIOS name cache</td></tr>
<tr><td>DNS</td> <td>WINS</td> <td>NetBIOS Broadcast</td> <td>WINS</td> <td>NetBIOS Broadcast</td></tr>
<tr><td>WINS</td> <td>NetBIOS Broadcast</td> <td>LMHOSTS file </td> <td>HOSTS file</td> <td>LMHOSTS file</td></tr>
<tr><td>NetBIOS Broadcast</td><td>LMHOSTS file</td> <td>WINS </td> <td>DNS</td> <td>HOSTS file</td></tr>
<tr><td>LMHOSTS file </td><td>HOSTS file</td> <td>HOSTS file </td> <td> </td> <td>DNS</td></tr>
<tr><td> </td><td>DNS</td> <td>DNS </td> <td> </td> <td></td></tr>
</table>

- [Configure host name resolution order in Win9x/WinMe](/article/win9x-host-name-resolution.html)
- [Configure host name resolution order in WinNT/Win2k](/article/winnt-host-name-resolution.html)
 
 More Info <a href="https://www.bing.com/search?q=KB%20119493%20Q119493" rel="nofollow" title="NetBIOS over TCP/IP Name Resolution and WINS [Q119493]">MS KB119493</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20172218%20Q172218" rel="nofollow" title="Microsoft TCP/IP Host Name Resolution Order [Q172218]">MS KB172218</a>  
 More Info <a href="https://www.bing.com/search?q=KB%20173161%20Q173161" rel="nofollow" title="How WINS Lookup Works from Windows NT DNS [Q173161]">MS KB173161</a>  